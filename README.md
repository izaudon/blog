# Top

いざうどん

{% assign categories = site.posts | map: "categories" | flatten | uniq | sort %}

{% for category in categories %}
  <h2>📁 {{ category }}</h2>
  <ul>
    {% for post in site.posts %}
      {% if post.categories contains category %}
        <li>
          <a href="{{ post.url }}">{{ post.title }}</a>
          <small>{{ post.date | date: "%Y-%m-%d" }}</small>
        </li>
      {% endif %}
    {% endfor %}
  </ul>
{% endfor %}