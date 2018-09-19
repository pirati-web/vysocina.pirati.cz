---
layout: page
title: Komunální volby v ostatních obcích
description: Kandidátní listina a program koalice Pojďme To Změnit.
keywords: lidé, členové, piráti, pirátky, příznivci, kandidátka, volby
---

## Komunální volby v ostatních obcích

<div class="o-section">
  <div class="row">
    {% if programCategories.size > 0 %}    
      <div class="columns medium-8">
    {% else %}    
      <div class="columns medium-12">
    {% endif %}    
      <div class="o-section-header o-section-header--bordered">
        <h3 class="o-section__heading t-h2-super">Kandidátní listina</h3>
      </div>
      <div class="c-program-candidates">

        {% assign leaderCandidate = site.people | where: "uid", candidates.leader.uid | first %}
        {% include candidate-badge.html candidate=candidates.leader candidatePage=leaderCandidate rank=1 %}

        {% if candidates.head.size %}
            {% for candidate in candidates.head %}
              {% assign candidatePage = site.people | where: "uid", candidate.uid  | first %}
              {% assign candidateRank = forloop.index | plus: 1 %}
              {% include candidate-badge.html candidate=candidate candidatePage=candidatePage leader=false rank=candidateRank %}
            {% endfor %}
        {% endif %}

        {% if candidates.tail.size > 0 %}
          <div class="c-program-candidates__others">
            {% for candidate in candidates.tail %}
              <p>
                <div itemprop="description" class="c-content-block c-emphasized-text">
                {% assign candidateRank = forloop.index | plus: 1 | plus: candidates.head.size %}
                <strong> {{ candidateRank }}.
                    {% if candidate.uid %} 
                        {% assign candidatePage = site.people | where: "uid", candidate.uid | first %}
                        <a href={{candidatePage.url}}> {% include people/fullname.html person=candidatePage %}</a>{% if candidate.age or candidate.profession or candidate.party %}, {% endif %}
                    {% else %}
                        {{ candidate.name }}{% if candidate.age or candidate.profession or candidate.party %}, {% endif %}
                    {% endif %}
                </strong>

                {% if candidate.age %}
                    {{ candidate.age }} let{% if candidate.profession or candidate.party %}, {% endif %}
                {% endif %}
                {% if candidate.profession %}
                    {{ candidate.profession }}{% if candidate.party %}, {% endif %}
                {% endif %}
                {% if candidate.party %}
                    {{ candidate.party }}
                {% endif %}
                </div>
              </p>
            {% endfor %}
          </div>
        {% endif %}

      </div>

      {% if candidates.note %}
        <p><strong>Pozn.:</strong> {{ candidates.note }}</p>
      {% endif %}
    </div>
    {% if programCategories.size > 0 %}    
    <div class="columns medium-4">
      <div class="o-section-header o-section-header--bordered">
        <h3 class="o-section__heading t-h2-super">Program</h3>
      </div>
      <div class="c-program-items">
          {% for category in programCategories %}
          <div class="c-program-items__item">
            <div class="c-program-items__item-wrap c-tile c-tile--fill">
              <div class="c-program-items__item-inner c-tile__body">
                <a href="{{ category.url | relative_url }}">
                  <h3 class="c-program-items__item-title c-headline-anchor t-h4">{{ category.title }}</h3>
                  <p>{{ category.perex }}</p>
                </a>
              </div>
            </div>
          </div>
          {% endfor %}
      </div>
    </div>
    {% endif %}    
  </div>
</div>
