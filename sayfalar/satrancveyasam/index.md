---
title: Satranç ve Yaşam
layout: default
---

### Satranç ve Yaşam  

<br>
<ul>

{%- for page in site.pages -%}


{%- if page.path contains "satrancveyasam" -%}

{%- unless page.path contains "index" -%}

    <li><a href="{{site.github.url}}{{page.url}}"> {{page.title}}</a> </li>

{%- endunless -%}

{%- endif -%}

{%- endfor -%}
</ul>
