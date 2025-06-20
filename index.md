---
layout: default
---

{% for post in site.posts %}

  <div class="post" id="post-{{ post.id }}">
    <h2><a href="{{ post.url | relative_url }}" rel="bookmark" title="Link permanente para {{ post.title }}">{{ post.title }}</a></h2>
    <small>{{ post.date | date: "%B %-d, %Y" }}</small>

    <div class="entry">
      {{ post.excerpt }}
      <p><a href="{{ post.url | relative_url }}">Leia o resto deste post &raquo;</a></p>
    </div>

    <p class="postmetadata">
      Postado em {% for category in post.categories %}{{ category }}{% unless forloop.last %}, {% endunless %}{% endfor %}
      |
      <a href="{{ post.url | relative_url }}#comments">Comentários</a>
    </p>
  </div>

{% endfor %}
