---
title: "[GitHub Blog #7] 검색에 노출시키기 - 구글·네이버 등록"
excerpt: "서치콘솔과 서치어드바이저에 등록하고 사이트맵을 제출해, 검색 결과에 내 글이 뜨게 만듭니다."
header:
  teaser: /
categories:
  - Web
tags:
  - GitHubBlog
  - GitHub
  - SEO
published: true
toc: true
toc_sticky: true
toc_label: GitHub Blog
date: 2026-06-13
last_modified_at: 2026-06-13
typora-root-url: ../
---

> 📚 GitHub 블로그 만들기 시리즈 #7 · [목차 보기](#)

## 이번 편에서 할 것
- ✅ 결과물: 구글·네이버에서 내 글이 검색된다
- 블로그를 만들어도 등록 안 하면 아무도 못 찾아온다 (특히 네이버)

## 1. 준비물 점검
- sitemap.xml, robots.txt, RSS가 잘 나오는지 확인
- description 채우기 (검색 스니펫 품질)

## 2. 구글 — Search Console
- **URL 접두어** 속성으로 등록 (도메인 방식 X — github.io는 DNS 못 씀)
- HTML 파일 인증 → 저장소 루트에 올리고 커밋
- Sitemaps에서 `sitemap.xml` 제출
- "사이트맵을 읽을 수 없음"은 보통 제출 직후 일시 상태 (기다리면 됨)

## 3. 네이버 — 서치어드바이저
- 사이트 등록 → HTML 파일 인증 → 소유확인
- 사이트맵 + RSS 제출
- 실제 노출까지 며칠~2주 소요

## 4. 확인하는 법
- `site:내주소`로 색인 여부 검색

## 다음 편
- **#8 방문자 분석 & 댓글**

<!-- TODO: 서치콘솔/서치어드바이저 화면 캡처 -->
