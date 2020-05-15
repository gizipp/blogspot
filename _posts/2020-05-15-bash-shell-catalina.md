---
layout: post
title: Cara mengubah default shell di catalina
shorttitle: Bash shell catalina
description: Cara mengubah shell bawaan di MacOS Catalina dari dan atau ke bash / zsh.
category:
tags:
  - bash
  - shell
  - catalina
last_modified_at: 2020-05-15
---

Semenjak macOS Catalina, shell bawaan di masOS adalah zsh. Yay!

Kebetulan saya sendiri lebih suka zsh. Namun adakalanya saya tetap memerlukan bash. Untungnya sebenarnya Apple tidak benar-benar menghapus bash di Catalina.

Cukup mengetikkan `bash` di terminal, kita sudah bisa menggunakan bash.

Namun, bagaimana jika memang memerlukan bash sebagai default bash? Yang artinya saat membuka terminal, yang keluar adalah langsung bash.

Mudah!

## Cara mengubah default shell (menjadi bash)?

Dengan perintah `chsh` kita dapat mengubah default shell kita.

```
chsh -s /bin/bash
```
:bulb: Agar lebih mudah mengingat, ch ialah change alias mengubah, sedang sh ialah shell. Maka chsh adalah change shell alias mengubah shell.

## Bagaimana untuk mengubah ke shell lain atau kembali ke zsh?

Cukup dengan perintah seperti ini.

```
chsh -s /bin/zsh
```

Untuk melihat daftar shell yang ada di komputer kamu gunakan `cat etc/shells`

<amp-img src="/assets/post/shell/shell-list.png" width="900" height="678" layout="responsive" alt="AMP"></amp-img>

#### Referensi

* [How to Change the Default Shell to Bash on macOS Catalina](https://go.gizipp.com/https://www.howtogeek.com/444596/how-to-change-the-default-shell-to-bash-in-macos-catalina/)
