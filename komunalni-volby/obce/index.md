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

        {% assign leaderCandidate = site.people | where: "uid", candidates.leader.uid | first %}
        {% include candidate-badge.html candidate=candidates.leader candidatePage=leaderCandidate %}

      </div>

  </div>
</div>
