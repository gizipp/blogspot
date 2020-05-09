---
layout: post
title: Perbedaan string kutip satu dan kutip dua di Ruby
description: Perbedaan string literal kutip satu 'string' dan kutip dua "string" di Ruby
tags: Ruby
---

Saat pertama-tama awal ngoding, saya bertanya-tanya bertanya-tanya, kenapa saat mendeklarasikan string kadang menggunakan `"my string"` atau `'my string'`

Awalnya, saya kira ini masalah preferensi sintaks saja.

Untuk mempermudah


## Perbedaan string literal kutip satu dan kutip dua di Ruby

Perbedaan utama antara keduanya adalah string literal dengan petik dua mendukung interpolasi string dan escape karakter yang lebih lengkap.

Bingung?

Show me the code saja ya.

## Single-quoted strings aka Petik Satu

```ruby
# Single-quoted string tidak mendukung interpolasi
puts 'Now is #{Time.now}'
# Now is #{Time.now}

# Double-quoted strings mendukubng interpolasi
puts "Now is #{Time.now}"
# Now is 2016-07-21 12:43:04 +0200
```

Pada Single-quoted string Time.now akan dicetak Time.now sebagai string biasa.

## Double-quoted strings aka Petik Dua

Hal menarik lainnya, adalah dukungan escape characters. Malah baru tahu sekarang. Hahaha.

```ruby
puts 'Hello\nWorld'
# Hello\nWorld

puts "Hello\nWorld"
# Hello
# World
```

Escape characters semacam `\n` akan dicetak sebagai baris baru alias new line, bukan string `\n`.

## Best practice

Jika perlu string interpolation dan escape sequences, gunakan petik dua.

Praktek string literal ini juga ada di bahasa pemrograman lain, baik di PHP, JavaScript dan lain-lain.


## References

- [Beda String Petik Satu dan Dua di PHP](https://go.gizipp.com/https://kursuswebprogramming.com/perbedaan-string-petik-satu-dan-dua/)
- [Difference Between Single-Quoted and Double-Quoted](https://go.gizipp.com/https://riptutorial.com/ruby/example/2819/difference-between-single-quoted-and-double-quoted-string-literals)
