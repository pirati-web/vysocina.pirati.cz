---
layout: communal-elections
title: Krajské volby 2020
heroBgImg: articles/2020/kampan20/zahajenikampan.jpg
campaignGroupUid: 2020vys
campaignCategoryUid: 2020vys
candidateListUid: 2020vys
---

{% assign candidates = site.candidatelists | where: "uid", page.candidateListUid | first %}
{% capture mainContent %}
  <h1 class="head-alt-lg md:head-alt-xl text-center">Krajské volby 2020</h1>
{% endcapture %}

{% capture subContent %}
  <h2 class="head-alt-base md:head-alt-md mt-2 text-center">Kraj středem pozornosti</strong></h2>
{% endcapture %}

{% include elections-header.html img=page.img bgImg=page.heroBgImg mainContent=mainContent subContent=subContent candidateListNumber=candidates.number %}

<!-- <div class="mt-4 md:mt-8 space-y-4">
  {% include buttons/icon.html icon="ico--chevron-right" cta="Program" class="btn--cyan-200 btn--hoveractive btn--fullwidth md:btn--autowidth text-lg" %}
  {% include buttons/icon.html icon="ico--chevron-right" cta="Kandidáti" class="btn--blue-300 btn--hoveractive btn--fullwidth md:btn--autowidth text-lg" %}
</div> -->
