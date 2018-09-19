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
<div class="c-program-candidate-badge">
  <a class="c-program-candidate-badge__body" href="{{ include.candidatePage.url | relative_url }}">
      <div class="c-program-candidate-badge__avatar">
          {% capture img %}{% if include.candidatePage.img %}{% asset '{{ include.candidatePage.img }}' magick:resize='225x225^' magick:gravity='center' magick:crop='225x225+0+0' @path %}{% else %}{{ 'assets/img/people/unknown-pirate.svg' | relative_url }}{% endif %}{% endcapture %}
          <img src="{{ img }}" alt="{% include people/fullname.html person=include.candidatePage plain=true %}" class="c-program-candidate-badge__avatar-image">
      </div>
      <div class="c-program-candidate-badge__description">
          <h4 class="c-program-candidate-badge__name"><span class="c-headline-anchor">{% include people/fullname.html person=include.candidatePage %}</span></h4>
          <strong class="c-program-candidate-badge__profession">
              {% if include.candidate.age %} {{ include.candidate.age }} let, {% endif %}
              {{ include.candidate.profession }}{% if include.candidate.party %}, {{ include.candidate.party }} {% endif %}
          </strong>
          {% if include.candidate.description %}
          <p class="c-program-candidate-badge__bio">{{ include.candidate.description }}</p>
          {% endif %}
      </div>
  </a>
</div>


      </div>

  </div>
</div>
