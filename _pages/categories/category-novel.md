---
title: "Novel"
layout: archive
permalink: categories/novel
author_profile: true
sidebar_main: true
---


{% assign posts = site.categories.Novel %}
{% for post in posts %} {% include archive-single.html type=page.entries_layout %} {% endfor %}
