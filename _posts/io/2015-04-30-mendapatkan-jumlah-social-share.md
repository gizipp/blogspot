---
layout: post
title: "Mendapatkan Jumlah Social Share Sebuah URL"
shorttitle: "Social Share Count"
desc: "Mendapat jumlah social share sebuah url di berbagai social media e.g twitter via API JSON."
category: io
tags: [api, socmed, json]
---

Beberapa waktu yang lalu diriku iseng membuat *crawler* sederhana dan sedikit sukses berhasil mengindeks url-url dalam sebuah blog/domain/web tertentu. Setelah mendapatkan url-url terkait, diriku penasaran kira-kira tersebut di *share* berapa kali.

## Twitter

>http://cdn.api.twitter.com/1/urls/count.json?url=http://stylehatch.co

## Facebook

>http://graph.facebook.com/?id=http://stylehatch.co

## Pinterest

    receiveCount({"url":"http://google.com","count":11278})

## LinkedIn

>https://www.linkedin.com/countserv/count/share?url=http://stylehatch.co&format=json

## Google Plus

### dengan api
    https://clients6.google.com/rpc?key=YOUR_API_KEY


### tanpa api
    require 'open-uri'
    require 'nokogiri'

    @url = "http://yoursite.com"

    googleplus_data = Nokogiri::HTML(open("https://plusone.google.com/_/+1/fastbutton?url=#{@url}"))
    self.gplus_count = googleplus_data.css('div#aggregateCount')[0].text.to_i


{% comment %}{% include ads.html %}{% endcomment %}


https://gist.github.com/jonathanmoore/2640302
https://gist.github.com/cmwinters/cc867a5be41707953d23
