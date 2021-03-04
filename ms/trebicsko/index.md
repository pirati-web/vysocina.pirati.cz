---
layout: codelame
description:
keywords:
title: Místní sdružení Třebíčsko
group:
  - name: Členové místního sdružení
    sort: ordpmstrebicsko
    category: mstrebicsko
---

Text v MARKDOWNu, takže můžete sami chystat obsah. Já vám to tam pak nahraju.

## Chápeme?

> Snad jo!

<div>
    {% if page.viewMode == 'grouped' %}
    {% for group in page.groups %}
      <section>
        {% assign team = site.people | where_exp: "item", "item.categories contains group.category" %}
        {% if group.sort %}
          {% assign team = team | sort: group.sort %}
        {% endif %}
        {% include people/list-group.html team=team teamName=group.name teamShortcut=group.category %}
      </section>
      {% unless forloop.last %}<hr class="hr--big" />{% endunless %}
    {% endfor %}
  {% else %}
    {% if page.category %}
      {% assign team = site.people | where_exp: "item", "item.categories contains page.category" %}
    {% else %}
      {% assign team = site.people %}
    {% endif %}

    {% if page.sort %}
      {% assign team = team | sort: page.sort %}
    {% endif %}

    <section>
      {% include people/list-responsive.html team=team %}
    </section>
  {% endif %}
</div>
