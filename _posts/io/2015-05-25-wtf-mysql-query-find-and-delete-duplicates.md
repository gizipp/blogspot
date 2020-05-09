---
layout: post
title: "WTF MySQL Query : Find & Delete Duplicates"
shorttitle: "WTF Mysql Query"
category: io
description: "Catatan MySQL Query untuk mencari dan menghapus duplikasi."
tags: [ngoding, mysql, catatan]
---

Berikut ini adalah catetan-catetan query MySQL agak tingkat lanjut yang agak-agak *fak!* untuk diingat-ingat, makanya daripada diingat, mending dicatat saja.

* Table of Contents
{:toc}

Semoga membantu diriku yang sedang di masa depan.

## Find Duplicates of Multiple Column

### tl;dr

{% highlight mysql %}
SELECT id, first_coloumn, second_coloumn, count(*)
FROM `agent_contacts`
WHERE `office_id`  =  '323'
GROUP BY first_coloumn, second_coloumn
HAVING count(*)>1
{% endhighlight %}

### csb

Mencari duplikasi pada banyak kolom tertentu, misalnya nama depan dan nama belakang. *Query*-nya adalah semacam ini :

{% highlight mysql %}
SELECT id, first_name, last_name, count(*)
FROM `agent_contacts`
WHERE `office_id`  =  '323'
GROUP BY first_name, last_name
HAVING count(*)>1
{% endhighlight %}

*Hint* utama dari *query* ini adalah ``HAVING count(*)>1`` alias lebih dari satu/duplikat.

> A HAVING clause in SQL specifies that an SQL SELECT statement should only return rows where aggregate values meet the specified conditions.

Dan juga berkat ```GROUP BY first_name, last_name``` ya.

>The GROUP BY statement is used in conjunction with the aggregate functions to group the result-set by one or more columns.

Nah jikalau ingin tambah email tinggal ``GROUP BY first_name, last_name, email`` atau jikalau mengecilkan cakupan kasih saja semacam ``WHERE `office_id`  =  '323'`` saja.

## Delete Duplicates of Multiple Column

### tl:dr

{% highlight mysql %}
DELETE from table_name
USING table_name, table_name as vtable
WHERE table_name.id <  vtable.id
AND (table_name.first_name=vtable.first_name)
AND (table_name.last_name=vtable.last_name)
{% endhighlight %}

### csb



Setelah bisa mencari duplikasi pada banyak kolom tertentu, misalnya nama depan dan nama belakang, lantas gimana menghapusnya duplikasinya? Tentu dengan menyisakan salah satu *row* darinya. *Query*-nya ialah kira-kira semacam ini :

{% highlight mysql %}
DELETE from `agent_contacts`
USING `agent_contacts`, `agent_contacts` as vtable
WHERE `agent_contacts`.id <  vtable.id
AND (`agent_contacts`.first_name=vtable.first_name)
AND (`agent_contacts`.last_name=vtable.last_name)
{% endhighlight %}

*Hint* utama dari *query* ini adalah alias ```USING  `agent_contacts`,  `agent_contacts` as vtable```

>SQL aliases (AS) are used to temporarily rename a table or a column heading.

Selanjutnya dengan logika semacam ``WHERE `agent_contacts`.id <  vtable.id`` untuk memilih mana yang mau dihapus. Kalau yang ingin dihapus yang lebih besar tinggal diganti ``WHERE `agent_contacts`.id >  vtable.id``

Atau untuk mengecilkan cakupan.

{% highlight mysql %}
DELETE from `agent_contacts`
USING  `agent_contacts`,  `agent_contacts` as vtable
WHERE `agent_contacts`.office_id  =  '323'
AND vtable.office_id  =  '323'
AND `agent_contacts`.id <  vtable.id
AND (`agent_contacts`.first_name=vtable.first_name)
AND (`agent_contacts`.last_name=vtable.last_name)
{% endhighlight %}


{% highlight mysql %}
SELECT *
FROM `agent_contacts`, `agent_contacts` as vtable
WHERE `agent_contacts`.`office_id` = '323'
AND vtable.`office_id` = '323'
AND `agent_contacts`.first_name = CONCAT(vtable.first_name,vtable.last_name)
{% endhighlight %}

{% highlight mysql %}
DELETE FROM `agent_contacts`
USING `agent_contacts`, `agent_contacts` as vtable
WHERE `agent_contacts`.`office_id` = '323'
AND vtable.`office_id` = '323'
AND `agent_contacts`.first_name = CONCAT(vtable.first_name,vtable.last_name)
{% endhighlight %}

{% highlight mysql %}
SELECT *
FROM `agent_contacts` , `agent_contacts` AS vtable
WHERE `agent_contacts`.`office_id` = '323'
AND vtable.`office_id` = '323'
AND CONCAT(`agent_contacts`.first_name,`agent_contacts`.last_name) = vtable.first_name
{% endhighlight %}
