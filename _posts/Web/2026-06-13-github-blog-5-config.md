---
title: "[GitHub Blog #5] _config.yml 길들이기 - 내 색깔 입히기"
excerpt: "프로필, 스킨, 폰트, About까지. 설정 파일 하나로 블로그에 내 색을 입힙니다."
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

> 📚 **GitHub 블로그 만들기 시리즈 #5** · [전체 목차](/web/github-blog-0-series-index/) · 이전: [#4 카테고리 구성](/web/github-blog-4-categories/) · 다음: [#6 HTML 손대기](/web/github-blog-6-customizing/)

이번 편의 목표.
> ✅ **내 색깔이 입혀진 블로그.**

블로그의 핵심 설정은 거의 다 **`_config.yml`** 한 파일에 모여 있어요. 코드를 깊이 안 건드려도, 이 파일만으로 꽤 많이 바꿀 수 있습니다.

> ⚠️ **가장 중요한 주의점:** `_config.yml`은 `jekyll serve` 중에 **자동 반영이 안 돼요.** 수정했으면 서버를 껐다 켜야 합니다.

## 1. 사이트 기본 정보

```yaml
title: "돼아리의 연구노트"          # 블로그 이름
description: "읽은 책과 일상을 기록하는 공간"  # 검색 결과에 보이는 설명
url: "https://iamlmj720.github.io" # 내 블로그 주소
logo: "/assets/img/logo.png"       # 마스트헤드 로고
```

> 💡 `description`은 비워두지 마세요. 검색 결과의 한 줄 설명으로 그대로 쓰여서, 비어 있으면 검색 품질이 떨어져요.

## 2. 작가 프로필 (사이드바)

글 옆/아래에 뜨는 내 프로필도 여기서 설정해요.

```yaml
author:
  name: "돼아리"
  avatar: "/assets/img/profile.jpeg"
  bio: "기록하는 사람 · 책과 순간을 모아둡니다 📚"
  location: "Seoul, Korea"
  links:
    - label: "GitHub"
      icon: "fab fa-fw fa-github"
      url: "https://github.com/iamlmj720"
    - label: "Instagram"
      icon: "fab fa-fw fa-instagram"
      url: "https://www.instagram.com/iamlmj720/"
```

소셜 링크는 `url`을 채운 항목만 표시돼요.

## 3. 스킨 바꾸기

minimal-mistakes는 색 테마(스킨)를 한 줄로 바꿀 수 있어요.

```yaml
minimal_mistakes_skin: "dark"
# air, aqua, contrast, dark, dirt, neon, mint, plum, sunrise ...
```

여러 개 바꿔보면서 마음에 드는 걸 고르면 됩니다.

## 4. About 페이지 꾸미기

블로그의 얼굴인 자기소개 페이지는 `_pages/about.md`에 있어요.

About에 넣으면 좋은 것들:
- **한 줄 소개** — 닉네임 유래, 블로그가 뭘 다루는 곳인지
- **다루는 주제** — 어떤 글이 올라오는지
- **연락처** — 댓글·소셜 링크로 자연스럽게

거창할 필요 없어요. "나는 이런 걸 기록하는 사람"이라는 한 문단이면 충분합니다.

## 다음 편

설정으로 바꿀 수 있는 건 다 바꿨다면, 이제 코드를 직접 만질 차례예요.
**[#6 레이아웃·HTML 손대기](/web/github-blog-6-customizing/)** 에서 테마 깊은 곳을 다룹니다.
