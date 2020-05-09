---
layout: post
title: "Konfigurasi MongoDB dan Mongoid di Rails 4.x"
shorttitle: "MongoDB+Mongoid di Rails"
description: "Langkah-langkah setup dan konfigurasi MongoDB dan Mongoid pada Ruby On Rails 4.x"
category: io
tags: [ruby, rails, mongodb, mongoid]
---

Di sini memakai Rails 4.2 namun seharusnya juga bisa untuk Rails 4.x

## Installasi mongodb

    sudo apt-key adv --keyserver keyserver.ubuntu.com --recv 7F0CEB10
    sudo echo "deb https://downloads-distro.mongodb.org/repo/ubuntu-upstart dist 10gen" | tee -a /etc/apt/sources.list.d/10gen.list
    sudo apt-get -y update
    sudo apt-get -y install mongodb-10gen

Test ketik ```mongo``` kalo sukses keluar *mongo shell*

## Setup Rails

### Kalau new project

    rails new myapp -O

    rails g mongoid:config

### Kalau existing project

Komen sqlite di Gemfile, tambah

    gem 'mongoid', '~> 4', github: 'mongoid/mongoid'
    gem 'bson_ext'

Di application.rb, activemodel dikomen, atau kira-kira seperti ini

    # Pick the frameworks you want:
    require "active_model/railtie"
    require "active_job/railtie"
    # require "active_record/railtie"
    require "action_controller/railtie"
    require "action_mailer/railtie"
    require "action_view/railtie"
    require "sprockets/railtie"
    require "rails/test_unit/railtie"
    require 'rails/mongoid'

Lalu

    rails g mongoid:config

Kalau masih error, cek semua konfig yang pake ```config.active_record```

Kalau sukses, test create model

    rails g model Post title:string body:string published:boolean

# Contoh Model

{% highlight ruby %}
class Post
  include Mongoid::Document

  field :title, type: String
  field :content, type: String
  field :category, type: String
  field :published, type: Boolean
end
{% endhighlight %}

Contoh Model Pake mongo slug

{% highlight ruby %}
class Post
  include Mongoid::Document
  include Mongoid::Slug

  has_one :category

  field :title, type: String
  field :content, type: String
  field :category, type: String
  field :published, type: Boolean

  slug :title
end
{% endhighlight %}

## Links

- https://gorails.com/blog/rails-4-0-with-mongodb-and-mongoid
- https://mongoid.org/en/mongoid/v3/querying.html

## Issue

### Mongodb Mongod Tidak Mau Jalan alias FAILED? Cek Log

Sudah menjadi standar untuk liat *log* tentunya. Apapun yang terjadi, jangan panik. Liat *log* dan jalan keluar pasti ada.

Dimana berkas log tersebut?

Biasanya dan seringnya ada pada `/var/log/mongod.log` secara *default*

Jika tidak tau, cek di file konfigurasi semcam `/etc/mongod.conf`

### ERROR: Insufficient free space for journal files



Jika mongod tidak mau jalan karena error tersebut

>ERROR: Insufficient free space for journal files
>Please make at least 422MB available in /data/journal or use --smallfiles

Dapat kamu gedein volumenya. Atau jika tidak mau, silahkan lakukan --smallfiles yang intinya pada mongod.conf tambahkan

    quota=true
    smallfiles=true

Lalu start server

### Error mongod

Jika tidak mau jalan karena *mongod.lock*

Cukup masuk dan hapus file *lock* ke e.g `/var/lib/mongod.lock`
