---
layout: post
title: "Assets Management Rails 4.x Dengan Bower"
shorttitle: "Rails+Bower Assets Management"
description: "Assets Management di Ruby On Rails 4.x dengan memanfaatkan Bower"
category: io
tags: [rails, bower]
---

## Requirement

Pastikan NPM sudah ada... lalu ```npm install -g bower``` agar global

## Inisiasi



Di folder roots rails bikin file ```.bowerrc``` (file configurasi bower sefolder bareng .gitignore) berisi...

    {
      "directory": "vendor/assets/components"
    }

```bower init``` dan lakukan setup semacam...

    {
      name: 'BowerAndRails',
      version: '0.0.1',
      authors: [
        'Syl <nop@nope.com>'
      ],
      description: 'Tutorial about Bower and Rails',
      license: 'MIT',
      homepage: 'https://mycoolhomepage.com',
      ignore: [
        '**/.*',
        'node_modules',
        'bower_components',
        'test',
        'tests'
      ],
      "dependencies": {
        "angular": "~1.2.16",
        "bootflat": "*"
      }
    }


Lalu sudah bisa ```bower install``` mirip ```bundle install`` setelah package ditaruh di depedensi.

# Configurasi di Rails

Di ```/config/application.rb``` tambahkan config assets...

    config.assets.paths << Rails.root.join('vendor', 'assets', 'components')

Assets sudah bisa digunakan... contohnya di ```application.css``` dan ```application.js`` ialah semacam

    //= require angular/angular
     *= require bootflat/bootstrap/bootstrap.min

dst... harus diingat pathnya bener.
