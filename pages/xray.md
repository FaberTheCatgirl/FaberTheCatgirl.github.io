---
layout: page
title: X-Ray
permalink: /docs/xray/
---


<p align="center">
<img src="/assets/img/Escape_sidorovitch_CS.png">
</p>

Welcome to the section dedicated to X-ray Engine. GSC provided official mod tools for the STALKER Trilogy which you can download through the offical website. 

Below are tutorials to aid you in working with the X-ray Engine including features within the tools and porting content.

<div class="section-index">
    <hr class="panel-line">
    {% for post in site.docs  %}   
        {% if post.section == "xray" %}  
            <div class="entry">
            <h5><a href="{{ post.url | prepend: site.baseurl }}">{{ post.title }}</a></h5>
            <p>{{ post.description }}</p>
            </div>
        {% endif %}
    {% endfor %}
</div>
