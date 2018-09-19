---
layout: page
title: Komunální volby v ostatních obcích
description: Kandidátní listina a program koalice Pojďme To Změnit.
keywords: lidé, členové, piráti, pirátky, příznivci, kandidátka, volby
candidateListUid: obce
---

<div class="o-section">
  <div class="row">
    {% if programCategories.size > 0 %}    
      <div class="columns medium-8">
    {% else %}    
      <div class="columns medium-12">
    {% endif %}    
      <div class="o-section-header o-section-header--bordered">
        <h3 class="o-section__heading t-h2-super">Vír</h3>
      </div>
      <div class="c-program-candidates">

        {% if candidates.head.size %}
            {% for candidate in candidates.head %}
              {% assign candidatePage = site.people | where: "uid", candidate.uid  | first %}
              {% assign candidateRank = forloop.index %}
              {% include candidate-badge.html candidate=candidate candidatePage=candidatePage leader=false rank=candidateRank %}
            {% endfor %}
        {% endif %}

      </div>

  </div>
</div>
