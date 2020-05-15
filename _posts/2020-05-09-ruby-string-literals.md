---
layout: post
title: Perbedaan string kutip satu dan kutip dua di Ruby
description: Perbedaan string literal kutip satu 'string' dan kutip dua "string" di Ruby
shorttitle: Ruby String Literal
desc: Memahami perbedaan utama string kutip satu (Single-quotes strings) dengan
  string kutip dua (Double-quoted strings) di bahasa pemograman Ruby.
tags:
  - ruby
  - string
  - pemula
last_modified_at: 2020-05-12
---
Saat pertama-tama awal ngoding, saya sering bertanya-tanya bertanya-tanya.

Kenapa saat mendeklarasikan *string* di Ruby kadang menggunakan petik satu `"my string"` atau petik dua `'my string'` ya?

Dan ini juga adakalanya ini berlaku di bahasa pemograman lainnya.

Awalnya, saya kira ini masalah preferensi sintaks atau *mood* programmer saja. Ternyata ada tujuan khusus.

## Apa perbedaan string kutip satu dan kutip dua di Ruby?

Perbedaan utama antara keduanya adalah string dengan petik dua mendukung interpolasi *string* dan *escape* karakter yang lebih lengkap.

Bingung?

*Show me the code* saja ya.

### Petik Satu aka Single-quoted strings tidak mendukukung interpolasi

```ruby
# String dengan petik satu tidak mendukung interpolasi
puts 'Waktu saat ini #{Time.now}'
# Waktu saat ini #{Time.now}

# String dengan petik dua mendukung interpolasi
puts "Waktu saat ini #{Time.now}"
# Waktu saat ini 2016-07-21 12:43:04 +0200
```

Pada string petik satu, Time.now akan dicetak Time.now sebuah *string* biasa.

Berbeda dengan *string* petik dua, yang akan benar-benar mencetak variabel waktu saat ini sebagai *string*, misal : 2016-07-21 12:43:04 +0200

Inilah yang dimaksud *string interpolation*.

### Petik Dua aka Double-quoted strings juga mendukung escape characters

Hal menarik lainnya, adalah mendukung *escape characters*.

Maksudnya? Lihat contoh berikut

```ruby
puts 'Hello\nWorld'
# Hello\nWorld

puts "Hello\nWorld"
# Hello
# World
```

Terlihat *escape* karakter semacam `\n` akan dicetak sebagai baris baru alias *new line*, bukan *string* `\n`.

Inilah yang disebut *escape sequences*.

## Kesimpulan

Praktek string literal ini sebenarnya juga ada di bahasa pemrograman lain, entah di PHP, JavaScript dan lain-lain, walaupun tidak 100% sama.

Di Ruby, jika perlu *string interpolation* dan *escape sequences*, gunakan petik dua. Selain itu bebas mau petik satu atau petik dua.

Sesederhana itu.

Bagaimana pemirsa, mudah bukan? Sajikan selagi hangat.

## Referensi

- [Beda String Petik Satu dan Dua di PHP](https://go.gizipp.com/https://kursuswebprogramming.com/perbedaan-string-petik-satu-dan-dua/)
- [Difference Between Single-Quoted and Double-Quoted](https://go.gizipp.com/https://riptutorial.com/ruby/example/2819/difference-between-single-quoted-and-double-quoted-string-literals)
