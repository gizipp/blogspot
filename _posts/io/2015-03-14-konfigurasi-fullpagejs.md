---
layout: post
title: "Konfigurasi fullpage.js"
shorttitle: "Konfigurasi fullpage.js"
description: "Konfigurasi devise untuk otentikasi."
category: io
tags: [js]
---

Contoh

```html
<div id="fullpage">
  <div class="section " id="section0">
    <div class="intro">
      <img src="https://raw.githubusercontent.com/alvarotrigo/fullPage.js/master/examples/imgs/1.png"  alt="1"/>
      <h1>Normal scrolling</h1>
      <p>With a linked menu</p>
    </div>
  </div>
</div>
```

Pas..
```javascript
<script type="text/javascript">
  $(document).ready(function() {
    $('#fullpage').fullpage({
      sectionsColor: ['#C63D0F']
    });
  });
</script>
```
Konfigurasi agak lengkap

```javascript
<script type="text/javascript">
  $(document).ready(function() {
    $('#fullpage').fullpage({
      menu: '#menu',
      anchors: ['firstPage', 'secondPage', '3rdPage'],
      sectionsColor: ['#C63D0F', '#1BBC9B', '#7E8F7C'],
      autoScrolling: false
    });
  });
</script>
```

Link : https://github.com/alvarotrigo/fullPage.js#fullpagejs
