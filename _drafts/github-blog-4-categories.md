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

> 📚 GitHub 블로그 만들기 시리즈 #4 · [목차 보기](#)

## 이번 편에서 할 것
- ✅ 결과물: 글이 분류되어 사이드바 메뉴에 뜬다

## 1. 카테고리 vs 태그
- 언제 뭘 쓰는지, 글 front matter에서 지정하는 법

## 2. 카테고리 페이지 만들기
- `_pages/categories/`에 카테고리별 `.md` 추가
- permalink와 `site.categories.키` 연결

## 3. 사이드바 메뉴 연결 (삽질 포인트)
- `_includes/nav_list_main`은 **자동이 아니라 직접 수정**해야 함
- 그룹 라벨 + 하위 카테고리 + 글 수 카운트 구조

## 4. 카테고리 목록 페이지 한글화
- `_layouts/categories.html`에서 키 → 한글 이름 매핑

## 다음 편
- **#5 _config.yml 길들이기**

<!-- TODO: 내 블로그 실제 카테고리 구조 예시로 설명 -->
