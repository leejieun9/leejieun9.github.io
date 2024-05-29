---
title: "JAVA"
layout: archive
permalink: /JAVA/
author_profile: true
sidebar:
    nav: "sidebar-category"
---

{% assign posts = site.categories.JAVA %}
{% for post in posts %} {% include archive-single.html type=page.entries_layout %} {% endfor %}
