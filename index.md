---
layout: index
---

<div class="home">
  <div class="container">
    <h2>API Resources</h2>
    <ul class="article-list">
      <li><a href="http://apidoc.olapic.com/" target="_blank">Olapic API v2.2</a></li>
      <ul>
      {% for article in site.articles %}
        {% if article.tags contains 'apiv2' %}
        <li><a href="{{ site.url }}{{ article.url }}">{{ article.title }}</a></li>
        {% endif %}
      {% endfor %}
      </ul>
      <li><a href="http://content-api-docs.photorank.me" target="_blank">Content API v1.0</a></li>
      <li><a href="http://data.photorank.me/api.html" target="_blank">Analytics API v1.0</a></li>
      <ul>
      {% for article in site.articles %}
        {% if article.tags contains 'analytics-api' %}
        <li><a href="{{ site.url }}{{ article.url }}">{{ article.title }}</a></li>
        {% endif %}
      {% endfor %}
      </ul>
    </ul>
    
    {% for cat in site.category-list %}
      {% if cat != "API Resources" %}
        <h2>{{ cat }}</h2>
        <ul class="article-list">
        {% assign sorted_articles = site.articles | sort: "order" %}
        {% for article in sorted_articles %}
          {% if article.resource == true %}
            {% for ac in article.categories %}
              {% if ac == cat %}
              <li><a href="{{ site.url }}{{ article.url }}">{{ article.title }}</a></li>
              {% endif %}   <!-- cat-match-p -->
            {% endfor %}  <!-- page-category -->
          {% endif %}   <!-- resource-p -->
        {% endfor %} <!-- page -->
        </ul>
      {% endif %}
    {% endfor %}  <!-- cat -->

  </div>
</div>
