---
layout: post
title: "Mendapatkan Jumlah Social Share Sebuah URL"
shorttitle: "Social Share Count"
description: "Mendapat jumlah social share sebuah url di berbagai social media e.g twitter via API JSON."
category: io
tags: [api, socmed, json]
---

Beberapa waktu yang lalu diriku iseng membuat *crawler* sederhana dan sedikit sukses berhasil mengindeks url-url dalam sebuah blog/domain/web tertentu. Setelah mendapatkan url-url terkait, diriku penasaran kira-kira tersebut di *share* berapa kali.

## Twitter

>https://cdn.api.twitter.com/1/urls/count.json?url=https://stylehatch.co

## Facebook

>https://graph.facebook.com/?id=https://stylehatch.co

## Pinterest

    receiveCount({"url":"https://google.com","count":11278})

## LinkedIn

>https://www.linkedin.com/countserv/count/share?url=https://stylehatch.co&format=json

## Google Plus

### dengan api
    https://clients6.google.com/rpc?key=YOUR_API_KEY


### tanpa api
    require 'open-uri'
    require 'nokogiri'

    @url = "https://yoursite.com"

    googleplus_data = Nokogiri::HTML(open("https://plusone.google.com/_/+1/fastbutton?url=#{@url}"))
    self.gplus_count = googleplus_data.css('div#aggregateCount')[0].text.to_i





https://gist.github.com/jonathanmoore/2640302
https://gist.github.com/cmwinters/cc867a5be41707953d23
