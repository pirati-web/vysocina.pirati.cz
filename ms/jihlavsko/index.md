---
layout: ms
description:
keywords:
title: Místní sdružení Jihlavsko
viewMode: grouped
groups:
  - name: Předsednictvo místního sdružení Jihlavsko
    sort: ordpmsjihlavsko
    category: pmsjihlavsko
  - name: Členové krajského místního sdružení Jihlavsko
    category: msjihlavsko
---

Místní sdružení Jihlavsko vzniklo v roce 2018. Ve stejném roce se Piráti dostali i do jihlavského zastupitelstva, do kterého kandidovali jako součást koalice Žijeme Jihlavou. V rámci příprav na příští volební období se členové a členky MS rozhodli vytvořit platformu, která umožní i zapojení nezávislých osobností a zároveň prosazování progresivní a sociálně liberální politiky. Kandidovat bude pod značkou Piráti a Fórum Jihlava.


<br><br>

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
      {% unless forloop.last %}<br><br>{% endunless %}
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
