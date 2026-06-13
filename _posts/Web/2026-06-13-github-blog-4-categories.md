---
title: "[GitHub Blog #4] 카테고리·태그·사이드바 구성하기"
excerpt: "글을 분류하는 카테고리/태그를 만들고, 직접 수정해야 하는 사이드바 메뉴까지 연결합니다."
header:
  teaser: /
categories:
  - Web
tags:
  - GitHubBlog
  - GitHub
  - Jekyll
published: true
toc: true
toc_sticky: true
toc_label: GitHub Blog
date: 2026-06-13
last_modified_at: 2026-06-13
typora-root-url: ../
---

> 📚 **GitHub 블로그 만들기 시리즈 #4** · [전체 목차](/web/github-blog-0-series-index/) · 이전: [#3 첫 글 쓰기](/web/github-blog-3-first-post/) · 다음: [#5 _config.yml](/web/github-blog-5-config/)

이번 편의 목표.
> ✅ **글이 분류되어 사이드바 메뉴에 뜬다.**

## 1. 카테고리 vs 태그

둘 다 글을 묶는 도구지만 쓰임이 달라요.

| | 카테고리 | 태그 |
|---|---|---|
| 성격 | 큰 분류(폴더) | 세부 키워드 |
| 개수 | 글당 1~2개 | 여러 개 자유롭게 |
| 예시 | `Web`, `Reading` | `GitHub`, `Jekyll`, `블로그` |

글 front matter에서 이렇게 지정해요.

```yaml
categories:
  - Web
tags:
  - GitHub
  - Jekyll
```

## 2. 카테고리 페이지 만들기

각 카테고리마다 모아 보여줄 페이지가 필요해요. `_pages/categories/` 안에 카테고리별 `.md` 파일을 둡니다.

```yaml
---
title: "Web"
layout: archive
permalink: /categories/web        # 이 카테고리 페이지 주소
author_profile: true
sidebar_main: true
---

{% raw %}{% assign posts = site.categories.Web %}
{% for post in posts %} {% include archive-single2.html type=page.entries_layout %} {% endfor %}{% endraw %}
```

`site.categories.Web` 의 `Web`이 front matter의 카테고리 이름과 맞아야 글이 모여요.

## 3. 사이드바 메뉴 연결 (삽질 포인트 ⚠️)

여기서 제가 한참 헤맸어요. **사이드바 카테고리 목록은 자동이 아니라, 직접 적어주는 구조**예요.
minimal-mistakes에서는 보통 `_includes/nav_list_main` 파일에 메뉴가 하드코딩되어 있습니다.

새 카테고리를 만들면 이 파일에도 손수 추가해야 메뉴에 보여요.

{% raw %}
```html
<!-- 글 수를 세는 변수 -->
{% assign web_count = site.categories.Web | default: '' | size %}

<!-- 메뉴에 추가 -->
<li>
  <span class="nav__sub-title">사이드 프로젝트</span>
  <ul>
    <li><a href="/categories/web">Web ({{ web_count }})</a></li>
  </ul>
</li>
```
{% endraw %}

`nav__sub-title`은 메뉴를 묶는 **그룹 라벨**일 뿐, 클릭되는 실제 카테고리는 그 아래 `<li>`예요.

## 4. 카테고리 목록 페이지 한글화

`/categories/` 전체 목록 페이지는 카테고리 이름을 영문 키로 보여줘요.
한글로 표시하려면 `_layouts/categories.html` 의 매핑에 한 줄 추가합니다.

```liquid
{% raw %}{% case category[0] %}
  {% when "Web" %}
    {% assign category_name = "Web" %}
  {% when "Reading" %}
    {% assign category_name = "독서모임" %}
{% endcase %}{% endraw %}
```

## 5. 폴더로 글 정리하기 (팁)

글이 많아지면 `_posts` 안을 `_posts/Web/`, `_posts/Reading/` 처럼 폴더로 묶어도 돼요.

> 💡 **`_posts` 하위 폴더는 카테고리로 추가되지 않아요.** (카테고리가 폴더에서 생기는 건 `_posts`보다 *상위* 폴더일 때예요.) 그래서 폴더로 정리해도 URL과 카테고리는 그대로 유지됩니다.

## 다음 편

이제 분류가 끝났으니, 블로그에 내 색을 입힐 차례예요.
**[#5 _config.yml 길들이기](/web/github-blog-5-config/)** 로 갑니다.
