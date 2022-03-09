---
title: "Novel"
layout: archive
permalink: categories/novel
author_profile: true
sidebar_main: true
---


{% assign posts = site.categories.novel %}
{% for post in posts %} {% include archive-single2.html type=page.entries_layout %} {% endfor %}
