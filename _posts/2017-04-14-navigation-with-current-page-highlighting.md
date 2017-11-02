---
layout: post
categories: [Development, Jekyll]
tags: [dev, jekyll, ssl]
---

Add navigation links to a data file in `_data/navigation.yml`:

```yaml
# Menu navigation links

- title: Home
  url: /

- title: Blog
  url: /blog/
```

Create `_includes/navigation.html` file:


{% raw %}
```liquid
{% for link in site.data.navigation %}
    {% if link.url contains 'http' %}
        {% assign domain = '' %}
    {% else %}
        {% assign domain = relative_url %}
    {% endif %}
    {% if link.url == page.url %}
        {% assign current = ' class="uk-active"' %}
    {% else %}
        {% assign current = null %}
    {% endif %}
    {% if link.title %}
        <li{{ current }}><a href="{{ domain }}{{ link.url }}" {% if link.url contains 'http' %}target="_blank" {% endif %}>{{ link.title }}</a></li>
    {% endif %}
{% endfor %}
```
{% endraw %}
