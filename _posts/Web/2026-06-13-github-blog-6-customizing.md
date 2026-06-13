---
title: "[GitHub Blog #6] 레이아웃·HTML 손대기 - 기본 테마 벗어나기"
excerpt: "_includes와 _layouts 구조를 이해하고, 폰트와 본문 디자인을 직접 고쳐 테마 티를 벗습니다."
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

> 📚 **GitHub 블로그 만들기 시리즈 #6** · [전체 목차](/web/github-blog-0-series-index/) · 이전: [#5 _config.yml](/web/github-blog-5-config/) · 다음: [#7 검색 등록](/web/github-blog-7-search/)

이번 편의 목표.
> ✅ **기본 테마 티를 벗은 나만의 디자인.**

설정으로 안 되는 부분은 테마 코드를 직접 고쳐야 해요. 무섭게 들리지만, 구조만 알면 생각보다 단순합니다.

## 1. 테마 구조 이해하기

minimal-mistakes는 역할별로 폴더가 나뉘어 있어요.

| 폴더 | 역할 |
|---|---|
| `_layouts/` | 페이지의 **큰 틀** (글 페이지, 목록 페이지 등) |
| `_includes/` | 틀 안에 끼워지는 **조각** (헤더, 사이드바, 푸터 등) |
| `_sass/` · `assets/css/` | **디자인(CSS)** |
| `_data/` | 메뉴 등 **데이터** |

블로그 화면 = `_layouts`(틀) + `_includes`(조각)들의 조합이라고 보면 돼요.

## 2. 테마 파일 덮어쓰기 원리

remote_theme(원격 테마) 방식을 쓰면 테마 파일이 내 저장소엔 안 보일 수 있어요.
그럴 땐 **원본 테마에서 고치고 싶은 파일만 내 저장소의 같은 경로로 복사**하면, 내 파일이 원본을 덮어씁니다.

```
예) 사이드바를 고치고 싶다
→ 테마의 _includes/nav_list_main 을
→ 내 저장소 _includes/nav_list_main 으로 복사 후 수정
```

## 3. 자주 건드리는 곳

- **사이드바** — `_includes/nav_list_main` (카테고리 메뉴, [#4](/web/github-blog-4-categories/)에서 다룸)
- **헤더/푸터** — `_includes/masthead.html`, `_includes/footer.html`
- **본문 스타일** — `_sass` 또는 `assets/css/main.scss`

## 4. 커스텀 폰트 적용하기

블로그 분위기는 폰트가 절반이에요. 웹폰트를 불러와 적용해봅니다.

```scss
/* assets/css/main.scss 등에 추가 */
@import url('https://fonts.googleapis.com/...');

body {
  font-family: 'NanumGothic', sans-serif;
}
```

제목과 본문에 서로 다른 폰트를 줘서 개성을 낼 수도 있어요.

## 5. 주의할 점

> ⚠️ 테마를 직접 고칠 때 두 가지를 조심하세요.
> 1. **테마 업데이트 충돌** — 내가 덮어쓴 파일은 테마가 업데이트돼도 안 바뀌어요. 가끔 원본과 비교가 필요합니다.
> 2. **백업 습관** — 큰 수정 전엔 `git commit`으로 저장해두면, 망쳐도 되돌리기 쉬워요.

## 다음 편

이제 보기 좋은 블로그가 됐어요. 그런데 아무도 못 찾아오면 소용없겠죠?
**[#7 검색에 노출시키기](/web/github-blog-7-search/)** 가 사실 이 시리즈에서 제일 중요한 편일지도 몰라요.
