---
layout: page
title: "Posts"
permalink: /posts
---
<div class="home">
  {% if site.paginate %}
    {% assign posts = paginator.posts %}
  {% else %}
    {% assign posts = site.posts %}
  {% endif %}


  {%- if posts.size > 0 -%}
      <h2 class="post-list-heading">Developer Blog</h2>
    <ul class="post-list">
      {%- for post in posts -%}
      <li>
          <span style="font-family: monospace">{{ post.date | date: "%b  %d, %Y" }}</span> - <a class="post-link" href="{{ post.url | relative_url }}">{{ post.title | escape }}</a> 
      </li>
      {%- endfor -%}
    </ul>

    {% if site.paginate %}
      <div class="pager">
        <ul class="pagination">
        {%- if paginator.previous_page %}
          <li>
            <a href="{{ paginator.previous_page_path | relative_url }}" class="previous-page" title="Go to Page {{ paginator.previous_page }}">
              {{ paginator.previous_page }}
            </a>
          </li>
        {%- else %}
          <li><div class="pager-edge">•</div></li>
        {%- endif %}
          <li><div class="current-page">{{ paginator.page }}</div></li>
        {%- if paginator.next_page %}
          <li>
            <a href="{{ paginator.next_page_path | relative_url }}" class="next-page" title="Go to Page {{ paginator.next_page }}">
              {{ paginator.next_page }}
            </a>
          </li>
        {%- else %}
          <li><div class="pager-edge">•</div></li>
        {%- endif %}
        </ul>
      </div>
    {%- endif %}
  {%- endif -%}
</div>