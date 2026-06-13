---
title: "전공노트"
layout: archive
permalink: /categories/major-notes
author_profile: true
sidebar_main: true
---

{% assign posts = site.categories.MajorNotes %}
{% for post in posts %} {% include archive-single2.html type=page.entries_layout %} {% endfor %}
