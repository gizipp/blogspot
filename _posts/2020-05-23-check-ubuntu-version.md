---
layout: post
title: Cara mencari tahu versi Ubuntu
shorttitle: Mencari Versi Ubuntu
description: Cara mencari versi Ubuntu di komputer kita, gunakan `lsb_release` atau `hostnamectl` maupun via GUI desktop.
category:
tags:
  - version
  - ubuntu
  - tutorial
last_modified_at: 2020-05-23
---

Gunakan `lsb_release` seperti ini `lsb_release -a`

```
No LSB modules are available.
Distributor ID:	Ubuntu
Description:	Ubuntu 18.04.4 LTS
Release:	18.04
Codename:	bionic
```

Atau versi singkat `lsb_release -d`

```
Description:	Ubuntu 18.04.4 LTS
```

### Cara lain

Bisa gunakan `hostnamectl`

```
Static hostname: localhost
      Icon name: computer-vm
        Chassis: vm
     Machine ID: 8bc38c38a48b464f8fd7db5d5b59ba87
        Boot ID: 788f7ad6b7614cfc9ac104bf9b834601
 Virtualization: kvm
Operating System: Ubuntu 18.04.4 LTS
         Kernel: Linux 4.15.0-88-generic
   Architecture: x86-64
```

***

Mudah bukan?

## Referensi

* [https://linuxize.com/post/how-to-check-your-ubuntu-version/](https://go.gizipp.com/https://linuxize.com/post/how-to-check-your-ubuntu-version/)
