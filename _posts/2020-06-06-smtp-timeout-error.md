---
layout: post
title: "Konfigurasi SMTP error : Net::OpenTimeout (execution expired) pada Rails, etc"
shorttitle: SMTP Error Timeout
description: 'Ketika error konfigurasi SMTP : Net::OpenTimeout (execution expired) pada Rails, etc, solusinya ganti port 2525'
category:
tags:
  - smtp
  - rails
  - tips
last_modified_at: 2020-06-06
---

Ketika SMTP error timeout. Jika di Ruby/Rails seperti ini :

```bash
Net::OpenTimeout (execution expired): net/smtp.rb:539:in `initialize`
```

Penyebabnya karena secara default kebanyakan ISP port 25 / 587 diblokir.

Solusinya diganti pakai port 2525

## Referensi:

* https://documentation.mailgun.com/en/latest/faqs.html#i-am-getting-timeouts-when-connecting-via-smtp-why
