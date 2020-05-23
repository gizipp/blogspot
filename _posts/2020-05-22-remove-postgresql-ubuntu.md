---
layout: post
title: Menghapus PostgreSQL di Ubuntu 18.04.1
shorttitle: Menghapus PostgreSQL
description: Menghapus PostgreSQL di Ubuntu 18.04.1
category:
tags:
  - postgresql
  - ubuntu
  - dpkg
last_modified_at: 2020-05-22
---

Sebelumnya, apakah cek apakah benar PostgreSQL sudah terpasang?

```
psql --version

# psql (PostgreSQL) 10.12 (Ubuntu 10.12-0ubuntu0.18.04.1)
```

Terlihat di mesin saya terpasang versi 10.12

***

Untuk mulai menghapus. Cek semua dependensi `postgres`

```
dpkg -l | grep postgres
```

Seperti ini kira-kira,

```
deploy@localhost:~$ dpkg -l | grep postgres

ii  postgresql-10                         10.12-0ubuntu0.18.04.1                          amd64        object-relational SQL database, version 10 server
ii  postgresql-10                  10.12-0ubuntu0.18.04.1                          amd64        front-end programs for PostgreSQL 10
ii  postgresql-client-common              190ubuntu0.1                                    all          manager for multiple PostgreSQL client versions
ii  postgresql-common                     190ubuntu0.1                                    all          PostgreSQL database-cluster manager
```

kita harus menghapus semuanya *(ditempat kamu mungkin berbeda)* antara lain : `postgresql-10`, `postgresql-client-10`, `postgresql-client-common`, `postgresql-common`

Hapus satu persatu dependensinya dengan perintah

```
sudo apt-get --purge remove command
```

Contohnya menghapus `postgresql-10`

```
sudo apt-get --purge remove postgresql-10
```

Ulangin hingga semua terhapus semua.

Atau hapus semuanya sekaligus gunakan perintah one-liner

```
sudo apt-get --purge remove pgdg-keyring postgresql-10 postgresql-client-10 postgresql-client-common postgresql-common
```

***

Jalankan lagi perintah apakah PostgreSQL masih terpasang, seharusnya sudah tidak ditemukan PostgreSQL

```
dpkg -l | grep postgres
```

Pastikan ulang, cek apakah benar PostgreSQL sudah terhapus?


```
deploy@localhost:~$ psql --version

Command 'psql' not found, but can be installed with:

sudo apt install postgresql-client-common
```

***

Mudah bukan?

## Referensi

* [https://www.liquidweb.com/kb/how-to-remove-postgresql/](https://go.gizipp.com/https://www.liquidweb.com/kb/how-to-remove-postgresql/)
