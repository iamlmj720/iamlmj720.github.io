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

> 📚 **GitHub 블로그 만들기 시리즈 #7** · [전체 목차](/web/github-blog-0-series-index/) · 이전: [#6 HTML 손대기](/web/github-blog-6-customizing/) · 다음: [#8 분석·댓글](/web/github-blog-8-analytics-comments/)

이번 편의 목표.
> ✅ **구글·네이버에서 내 글이 검색된다.**

블로그를 아무리 잘 만들어도, **검색 등록을 안 하면 아무도 못 찾아옵니다.** 특히 네이버는 등록 안 하면 거의 안 떠요. 이 편이 어쩌면 가장 중요한 편이에요.

## 1. 준비물 점검

등록 전에 이 세 가지가 잘 나오는지 확인하세요. (minimal-mistakes는 보통 기본 제공돼요.)

- `내주소/sitemap.xml` — 글 목록 지도
- `내주소/robots.txt` — 크롤러 안내
- `내주소/feed.xml` — RSS

그리고 `_config.yml`의 `description`을 꼭 채워주세요. 검색 결과 한 줄 설명에 쓰입니다.

## 2. 구글 — Search Console

1. [Google Search Console](https://search.google.com/search-console) 접속
2. 속성 추가 → **"URL 접두어"** 선택 *(도메인 말고!)*
3. 내 블로그 주소 입력 → **HTML 파일** 인증 방식 선택
4. 받은 인증 파일을 저장소 **루트**에 올리고 커밋·푸시 → "확인" 클릭
5. 인증되면 **Sitemaps** 메뉴에서 `sitemap.xml` 제출

> ⚠️ **`github.io` 주소는 DNS(도메인) 인증을 못 써요.** GitHub 소유라 DNS 설정에 접근할 수 없거든요. 반드시 **"URL 접두어" + "HTML 파일"** 방식으로 하세요.

> 💡 사이트맵 제출 직후 **"사이트맵을 읽을 수 없음"** 이 떠도 당황하지 마세요. 구글이 아직 안 가져갔을 뿐, 보통 몇 시간~며칠 뒤 "성공"으로 바뀝니다.

## 3. 네이버 — 서치어드바이저

1. [네이버 서치어드바이저](https://searchadvisor.naver.com/) 접속
2. 사이트 등록 → **HTML 파일 업로드** 인증 → "소유확인"
3. **요청 → 사이트맵 제출**에 `sitemap.xml`
4. **요청 → RSS 제출**에 `feed.xml` (선택, 새 글 수집이 빨라짐)

> ⚠️ 네이버는 등록해도 실제 검색에 뜨기까지 **며칠~2주** 걸려요. 느긋하게 기다리면 됩니다.

## 4. 잘 됐는지 확인하는 법

며칠 뒤, 검색창에 이렇게 쳐보세요.

```
site:내주소   (예: site:iamlmj720.github.io)
```

내 글들이 결과로 나오면 색인이 된 거예요. 안 나오면 아직 수집 전이니 조금 더 기다리면 됩니다.

## 다음 편

검색으로 사람들이 찾아오기 시작하면, 이제 **누가 오는지** 궁금해져요.
**[#8 방문자 분석 & 댓글](/web/github-blog-8-analytics-comments/)** 에서 마무리합니다.
