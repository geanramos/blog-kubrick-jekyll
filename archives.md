---
layout: default
title: Arquivos do Blog
---

<h2>Arquivos por Mês:</h2>
<ul>
  {% assign postsByMonth = site.posts | group_by_exp:"post", "post.date | date: '%B de %Y'" %}
  {% for month in postsByMonth %}
    {% assign first_post_in_month = month.items | first %}
    <li>
      <a href="{{ site.baseurl }}/arquivos/{{ first_post_in_month.date | date: '%Y/%m' }}/">
        {{ month.name }}
      </a> 
      ({{ month.items | size }})
    </li>
  {% endfor %}
</ul>

<hr>

<h2>Arquivos por Assunto (Categorias):</h2>
<ul>
  {% for category in site.categories %}
    <li>
      <a href="{{ site.baseurl }}/categorias/{{ category | first | slugify }}/">
        {{ category | first }}
      </a> 
      ({{ category | last | size }})
    </li>
  {% endfor %}
</ul>
