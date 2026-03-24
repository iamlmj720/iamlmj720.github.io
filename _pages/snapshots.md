---
title: "Snapshots"
layout: archive
permalink: /snapshots/
author_profile: false
sidebar_main: false
entries_layout: grid
classes: wide
---

사진과 짧은 기록을 모아두는 공간입니다.

{% assign snapshots = site.snapshots | sort: "date" | reverse %}
{% assign visible_snapshots = snapshots | where_exp: "item", "item.hidden != true" %}

{% if visible_snapshots.size > 0 %}
  <div class="entries-{{ page.entries_layout | default: 'grid' }}">
    {% for post in visible_snapshots %}
      {% include archive-single.html type=page.entries_layout %}
    {% endfor %}
  </div>
{% else %}
  <div class="notice--info">
    아직 등록된 snapshot이 없습니다. `_snapshots/`에 문서를 추가하고 이미지 파일은 `assets/img/snapshots/` 아래에 두면 됩니다.
  </div>
{% endif %}
