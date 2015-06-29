---
layout: post
title: "Menambah Foreign Key/References Dengan File Migrasi"
shorttitle: "Foreign Key/References Pada Rails"
excerpt: "Menambah foreign key atau references dengan file migrasi pada Rails 4.x"
category: io
tags: [ruby, rails]
---

Di Rails 4.x bisa dengan References

{% highlight ruby %}
rails g migration AddLinkRefToArticles link:references
{% endhighlight %}

File migrasi yang terjadi

{% highlight ruby %}
class AddLinkRefToArticles < ActiveRecord::Migration
  def change
    add_reference :articles, :link, index: true
    add_foreign_key :articles, :links
  end
end
{% endhighlight %}

Jika benar, di schema.rb bertambah field dan index

{% highlight ruby %}
t.integer  "link_id"
add_index "articles", ["link_id"], name: "index_articles_on_link_id"
{% endhighlight %}

Jangan lupa nambah relasi di model.

#MISC Links
[http://stackoverflow.com/questions/16257116/adding-foreign-key-to-a-rails-model](http://stackoverflow.com/questions/16257116/adding-foreign-key-to-a-rails-model)