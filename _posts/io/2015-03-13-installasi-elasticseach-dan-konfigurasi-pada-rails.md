---
layout: post
title: Install ElasticSearch dan Konfigurasi Pada Rails
shorttitle: ElasticSearch Pada Rails
description: "Langkah-langkah menginstall ElasticSearch dan melakukan konfigurasi pada Rails"
category: io
tags: [ruby, rails, elasticsearch]
---

ElasticSearch adalah penemuan keren di era big data. Atau sebaliknya? Big data dulu baru kepikiran mbikin semacam ElasticSeach.

Langkah-langkahnya adalah sesuai judulnya, yaitu


## Install ElasticSearch

Untuk install ES [disini](https:/go.gizipp.com/https://www.elastic.co/guide/en/elasticsearch/guide/current/_installing_elasticsearch.html) yang intinya perintah beginian saja. Versinya jangan lupa diganti.

    curl -L -O https://download.elasticsearch.org/PATH/TO/VERSION.zip
    unzip elasticsearch-$VERSION.zip
    cd  elasticsearch-$VERSION

Lantas jalankan server ES :

    sudo service elasticservice start

Untuk mengetest ES sudah jalan tidak, silahkan coba kau buka http:localhost:9200 bisakah? Jika bisa, maka selanjutnya tinggal configure di ES-nya.

##Konfigurasi Pada Rails



Gemfilenya adalah sbb

```ruby
gem 'elasticsearch', git: 'git://github.com/elasticsearch/elasticsearch-ruby.git'
gem 'elasticsearch-model', git: 'git://github.com/elasticsearch/elasticsearch-rails.git'
gem 'elasticsearch-rails', git: 'git://github.com/elasticsearch/elasticsearch-rails.git'
```
Di modelnya adalah sbb

```ruby
class Article < ActiveRecord::Base
  include Elasticsearch::Model
  include Elasticsearch::Model::Callbacks
  Article.import
end
```

## Tautan

- https://go.gizipp.com/https://www.elastic.co/guide/en/elasticsearch/guide/current/_installing_elasticsearch.html
