---
layout: post
title: "ActiveRecord Set Attibutes Rails 4"
description: "cara set attributes di rails 4"
category: io
tags: [rails]
---


Di Rails 4, cara mengubah attribut ActiveRecord makin beragam. Tiap-tiap method ada perbedaan yang tidak terlalu mencolok, namun sebenarnya sangat penting untuk dipahami secara mendalam sebab cukup berbahaya(?), salah pilih cukup menyeramkan(?), terutama masalah validasi dan callback.


Yang secara mendalam di sini https://davidverhasselt.com/set-attributes-in-activerecord/

### TL;DR

Kasus yang paling sering dipake.
+ Method .update ngecek validasi dan callback.
+ Method update_attribute bisa bypass validasi.
+ Pakai .update_column atau .update_columns kalau tidak ingin kena validasi dan callback, makanya updated_at tidak berubah.
+ Pake .touch untuk sekedar ubah updated_at
