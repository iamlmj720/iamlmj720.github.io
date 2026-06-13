---
title: "[GitHub Blog #8] 방문자 분석 & 댓글 달기"
excerpt: "Google Analytics로 방문자를 보고, 댓글 기능을 붙여 블로그를 살아있는 공간으로 만듭니다."
header:
  teaser: /
categories:
  - Web
tags:
  - GitHubBlog
  - GitHub
  - Analytics
published: true
toc: true
toc_sticky: true
toc_label: GitHub Blog
date: 2026-06-13
last_modified_at: 2026-06-13
typora-root-url: ../
---

> 📚 **GitHub 블로그 만들기 시리즈 #8 (마지막 편)** · [전체 목차](/web/github-blog-0-series-index/) · 이전: [#7 검색 등록](/web/github-blog-7-search/)

이번 편의 목표.
> ✅ **누가 얼마나 오는지 보이고, 댓글을 받을 수 있다.**

드디어 마지막 편이에요. 블로그를 "살아있는 공간"으로 만드는 두 가지, 분석과 댓글을 붙여봅니다.

## 1. Google Analytics 연결

방문자 통계를 보려면 Google Analytics(GA4)를 연결해요.

1. [Google Analytics](https://analytics.google.com/) 에서 속성 만들기
2. **측정 ID** 발급 (`G-XXXXXXXXXX` 형식)
3. `_config.yml`에 입력

```yaml
analytics:
  provider: "google-gtag"
  google:
    tracking_id: "G-XXXXXXXXXX"
    anonymize_ip: false
```

push 하면 방문 데이터가 쌓이기 시작해요.

## 2. 방문자 데이터 읽는 법

Analytics에서 자주 보게 되는 것들:

- **실시간** — 지금 몇 명이 보고 있는지
- **페이지별 조회수** — 어떤 글이 인기 있는지
- **유입 경로** — 구글 검색? 네이버? SNS?

> 💡 처음엔 방문자가 거의 없는 게 정상이에요. 검색 색인([#7](/web/github-blog-7-search/))이 자리 잡는 데 시간이 걸리니, 숫자에 일희일비하지 말고 글을 쌓는 데 집중하세요.

## 3. 댓글 기능 붙이기

GitHub 블로그는 정적 사이트라 댓글은 외부 서비스를 연결해요. 대표적으로 둘 중 하나를 씁니다.

| | Disqus | utterances |
|---|---|---|
| 기반 | 자체 서비스 | **GitHub 이슈** |
| 가입 | 별도 가입 필요 | 댓글 작성자가 GitHub 로그인 |
| 느낌 | 일반 블로그 댓글 | 개발자 친화적, 광고 없음 |
| 추천 | 일반 독자 많을 때 | 개발 블로그일 때 |

`_config.yml`의 `comments.provider`에 원하는 것을 지정하면 돼요.

```yaml
comments:
  provider: "disqus"   # 또는 "utterances"
  disqus:
    shortname: "내-disqus-shortname"
```

## 4. 마무리 — 시리즈를 닫으며

여기까지 오셨다면, 이제 블로그는 이런 상태예요.

- ✅ 인터넷에 떠 있고 ([#2](/web/github-blog-2-setup-deploy/))
- ✅ 글을 쓰면 쌓이고 ([#3](/web/github-blog-3-first-post/))
- ✅ 분류되어 정리되고 ([#4](/web/github-blog-4-categories/))
- ✅ 내 색깔이 입혀졌고 ([#5](/web/github-blog-5-config/), [#6](/web/github-blog-6-customizing/))
- ✅ 검색에 잡히고 ([#7](/web/github-blog-7-search/))
- ✅ 방문자와 댓글을 받는다 (이번 편)

이제 정말 **"글 쓰기"에만 집중할 수 있는 환경**이 완성됐어요.
처음엔 낯설지만, 한 번 구조를 익히면 이 블로그는 오래 함께 갈 기록 공간이 됩니다.
긴 시리즈 따라와 주셔서 고마워요. 이제 당신의 이야기를 채워나갈 차례예요. 🐷

> 전체 목차로 돌아가기 → **[#0 시리즈 목차](/web/github-blog-0-series-index/)**
