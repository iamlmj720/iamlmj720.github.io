---
title: "[GitHub Blog #1] GitHub 블로그란? 시작 전 큰 그림"
excerpt: "GitHub Pages, Jekyll, 테마가 어떻게 맞물려 블로그가 되는지 전체 그림부터 잡습니다."
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

> 📚 **GitHub 블로그 만들기 시리즈 #1** · [전체 목차](/web/github-blog-0-series-index/) · 다음: [#2 환경 세팅](/web/github-blog-2-setup-deploy/)

본격적으로 설치하기 전에, **무엇을 만들고 있는지 큰 그림부터** 그려두면 훨씬 덜 헤맵니다.
이번 편은 손으로 따라 하는 건 없고, 머릿속에 지도를 그리는 시간이에요.

## GitHub 블로그를 이루는 3가지

GitHub 블로그는 사실 한 덩어리가 아니라, 세 가지가 맞물려 돌아가는 구조예요.

| 구성요소 | 역할 | 비유 |
|---|---|---|
| **GitHub Pages** | 내 파일을 웹사이트로 띄워주는 무료 호스팅 | 가게 자리(터) |
| **Jekyll** | 마크다운 글을 HTML 블로그로 변환 | 인테리어 시공 |
| **테마** | 디자인·기능이 미리 짜인 틀 | 가구 세트 |

즉 **GitHub Pages라는 땅 위에, Jekyll로 지은 집을, 테마로 꾸미는** 그림이에요.

## 왜 GitHub 블로그인가

### 장점
- 💸 **무료** — 도메인만 안 사면 0원
- ✍️ **글 = 파일** — 글을 쓰면 마크다운 파일이 쌓여요. "기록"이 그대로 남습니다
- 🔧 **완전 커스텀** — 코드를 직접 고칠 수 있어 한계가 거의 없음
- 🧳 **종속 없음** — 플랫폼이 망해도 내 글(파일)은 내 손에

### 단점
- 처음엔 **구조 이해**에 시간이 듦 (이 시리즈가 그걸 줄여줄 거예요)
- 댓글·검색 같은 동적 기능은 **외부 서비스를 붙여야** 함

## 전체 작업 순서 미리보기

이 시리즈는 아래 순서로 진행됩니다.

1. **환경 세팅 & 배포** — 빈 블로그를 인터넷에 띄우기 ([#2](/web/github-blog-2-setup-deploy/))
2. **글쓰기** — 첫 글 발행 ([#3](/web/github-blog-3-first-post/))
3. **카테고리** — 글 분류와 메뉴 ([#4](/web/github-blog-4-categories/))
4. **커스터마이징** — 설정과 디자인 ([#5](/web/github-blog-5-config/), [#6](/web/github-blog-6-customizing/))
5. **검색·분석** — 사람들이 찾아오게 ([#7](/web/github-blog-7-search/), [#8](/web/github-blog-8-analytics-comments/))

## 어떤 테마를 쓰나요

저는 **[minimal-mistakes](https://mmistakes.github.io/minimal-mistakes/)** 테마를 사용합니다.

- 깔끔하고 군더더기 없는 디자인
- 한글 블로그에 쓰는 사람이 많아 **막혔을 때 검색할 자료가 풍부**
- 카테고리·태그·목차·검색 등 블로그에 필요한 기능이 기본 탑재

이 시리즈의 모든 예시도 minimal-mistakes 기준입니다.

## 다음 편

큰 그림을 그렸으니, 이제 실제로 손을 움직일 차례예요.
**[#2 로컬 환경 세팅 & 첫 배포](/web/github-blog-2-setup-deploy/)** 에서 빈 블로그를 인터넷에 띄워봅니다.
