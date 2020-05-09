---
layout: post
title: "Ruby On Rails Untuk Pemula"
title: "Rails Untuk Pemula"
description: "Langkah-langkah memulai belajar dan konfigurasi awal Ruby On Rails untuk pemula."
category: io
tags: [ruby, rails]
---


##  Install curl

ketik di terminal `curl` kalo belum ada install dulu kalo sudah ada skip

```bash
sudo add-apt-repository ppa:costamagnagianfranco/ettercap-stable-backports
sudo apt-get update
sudo apt-get install curl
```

### Install rvm

```bash
\curl -sSL https://get.rvm.io | bash -s stable

=> source /home/sari/.rvm/scripts/rvm
=> rvm
=> rvm list known
```

## Install Ruby

```bash
  rvm install 2.1.4
```

Kalau sukses cek `ruby -v`

## instal rails

    gem install rails

Tunggu sekitar 30 menitan tergantung koneksi internet. Biar cepet, boleh nggak usah install rdoc kek :

    gem install rails --no-rdoc --no-ri

Kalau sudah terinstall dan sukses check dengan commands `rails -v` harusnya:

    Rails 4.2.0

## MISC

## #menghilangkan can not find java run time

    sudo apt-get install nodejs libxslt-dev libxml2-dev libmysqlclient-dev

atau pada Gemfile bagian rubyracer di uncomments

### NEW rails project

    rails new nama_folder

masuk ke folder

    rails s /rails server

copy paste url yang ada di  Rails 4.1.8 application starting in development on https://0.0.0.0:3000 => Baris ke dua

https://guides.railsgirls.com/install/#setup-for-linux
