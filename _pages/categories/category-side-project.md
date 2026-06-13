---
title: "사이드 프로젝트"
layout: archive
permalink: /categories/side-project
author_profile: true
sidebar_main: true
---

{% assign posts = site.categories.SideProject %}
{% for post in posts %} {% include archive-single2.html type=page.entries_layout %} {% endfor %}
