---
layout: page
title: "Games"
permalink: /games
---

<div class="bm-game-list">
{% for item in site.data.games %}
<div class="bm-game-list-item">
<h2>
{% if item.link %}
<a href="{{ item.link | relative_url }}">
{% endif %}
<div class="bm-app-img"></div> {{ item.name }}
{% if item.link %}
</a>
{% endif %}
</h2>
<p>Released: {{ item.date }}</p>
{% if item.desc %}
<p>{{item.desc }}</p>
{% endif %}
</div>
{% endfor %}
</div>
