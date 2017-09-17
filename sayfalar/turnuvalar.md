---
title: Turnuvalar
permalink: turnuvalar/index.html
layout: default
---

<h3> Turnuvalar </h3>

{% assign myfiles = site.static_files | sort: 'name' | reverse %}
{% assign turnuva_sayisi = 0 %}

{%- for myfile in myfiles -%}

{%- if myfile.path contains 'data/turnuvalar/' -%}
{%- assign turnuva_sayisi = turnuva_sayisi | plus: 1 -%}
{%- endif -%}

{%- endfor -%}

<p>Bugüne kadar <strong> {{ turnuva_sayisi }} </strong> turnuva düzenlendi.</p>
<div class="row">

  <div class="col-md-12">
    <table class="table table-bordered table-striped">
    <tbody>
    <tr>
      <th>Turnuva Adı</th>
      <th>Detaylar</th>
      <th>Tarih</th>
    </tr>

    {%- for myfile in myfiles -%}

    {%- if myfile.path contains 'data/turnuvalar/' -%}

    {% assign tarih = myfile.basename | split: '-' %}
    {% assign tarihs = tarih[0] | append: '-' | append: tarih[1] | append: '-' | append: tarih[2] %}

    <tr>
    <td class="col-md-8"><a href="{{ site.github.url }}/turnuvalar/{{ myfile.basename }}" > {{ site.data.turnuvalar[myfile.basename].adi }} </a></td>
    <td class="col-md-2">
{%- if site.data.turnuvalar[myfile.basename].turnuva-durum == 1 -%}
<div style="font-size: 20px">
    <a href="{{ site.github.url }}/turnuvalar/{{ myfile.basename }}/yonerge" style="margin-right:5px"><span class="glyphicon glyphicon-calendar" aria-hidden="true"></span></a>
    <a href="{{ site.github.url }}/turnuvalar/{{ myfile.basename }}/sonuclar" style="margin-right:5px"><span class="glyphicon glyphicon-list-alt" aria-hidden="true"></span></a>
    <a href="{{ site.github.url }}/turnuvalar/{{ myfile.basename }}/fotograflar" style="margin-right:5px"><span class="glyphicon glyphicon-camera" aria-hidden="true"></span></a>
</div>
{%- else -%}
    <a href="{{ site.github.url }}/turnuvalar/{{ myfile.basename }}/basvuru" class="btn btn-primary center-block"><div class="faa-flash animated">Başvur</div></a>
{%- endif -%}

    </td>
    <td class="col-md-2 text-right">
    {{ tarihs | date: "%-d" }}
    {% assign m = tarihs | date: "%-m" | minus: 1 %}
    {{ site.data.tr.months[m] }}
    {{ tarihs | date: "%Y" }}
    </td>
    </tr>
    {%- endif -%}

    {%- endfor -%}

    </tbody>
    </table>
  </div>

</div>
