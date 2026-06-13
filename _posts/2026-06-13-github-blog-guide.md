---
title: "[Web] GitHub 블로그 사용법 - 시작부터 검색 등록까지"
excerpt: null
header:
  teaser: /
categories:
  - Web
tags:
  - GitHub
  - Jekyll
  - 블로그
published: true
toc: true
toc_sticky: true
toc_label: GitHub Blog
date: 2026-06-13
last_modified_at: 2026-06-13
typora-root-url: ../
---

블로그를 직접 만들어보니, 막상 시작은 쉬운데 "이건 어디서 바꾸지?" 싶은 순간이 계속 옵니다.
미래의 제가 다시 찾아볼 겸, 같은 길을 가는 분들도 덜 헤매시라고 GitHub 블로그 사용법을 정리해 둡니다.

## GitHub 블로그가 뭔가요

GitHub Pages는 GitHub 저장소에 올린 파일을 그대로 웹사이트로 띄워주는 무료 호스팅이에요.
여기에 **Jekyll**이라는 정적 사이트 생성기를 얹으면, 마크다운(`.md`)으로 글만 써도 알아서 블로그 형태로 변환해 줍니다.

- 💸 **무료** — 도메인만 안 사면 0원
- ✍️ **글 = 마크다운 파일** — 글 쓰는 게 곧 기록 파일이 쌓이는 것
- 🔧 **내 맘대로 커스텀** — 테마 코드를 직접 고칠 수 있음

저는 [minimal-mistakes](https://mmistakes.github.io/minimal-mistakes/) 테마를 사용했습니다. 깔끔하고 한글 블로그에 쓰는 사람이 많아 참고 자료가 풍부해요.

## 글은 어떻게 쓰나요

`_posts` 폴더에 **`YYYY-MM-DD-제목.md`** 형식으로 파일을 만들면 글 하나가 됩니다.
파일 맨 위 `---` 사이에 들어가는 부분을 **front matter**라고 부르고, 글의 설정값이에요.

```yaml
---
title: "글 제목"
categories:
  - Web        # 어떤 카테고리에 넣을지
tags:
  - GitHub
date: 2026-06-13
toc: true       # 목차 표시
---

여기부터 본문을 마크다운으로 작성합니다.
```

`categories` 값만 맞춰주면 해당 카테고리 페이지에 자동으로 글이 모입니다.

## 카테고리 추가하기

minimal-mistakes에서 카테고리는 보통 두 군데를 건드립니다.

1. **카테고리 페이지** — `_pages/categories/` 안에 카테고리별 `.md` 파일
2. **사이드바 목록** — `_includes/nav_list_main` 에 직접 적힌 메뉴

사이드바는 자동이 아니라 손으로 적어주는 구조라, 새 카테고리를 만들면 이 파일에도 한 줄 추가해야 메뉴에 보입니다. (저는 이걸 몰라서 한참 헤맸어요.)

{% raw %}
```html
<li><a href="/categories/web" class="">Web ({{ web_count }})</a></li>
```
{% endraw %}

## 검색에 뜨게 하기 (가장 중요)

블로그를 만들어도 **검색 등록을 안 하면 아무도 못 찾아옵니다.** 특히 네이버는 등록 안 하면 거의 안 떠요.

### 구글 — Search Console

1. [Google Search Console](https://search.google.com/search-console) 접속
2. 속성 추가 → **"URL 접두어"** 선택 (도메인 말고!)
3. 본인 블로그 주소 입력 → **HTML 파일** 인증 방식 선택
4. 받은 인증 파일을 저장소 **루트**에 올리고 커밋 → "확인" 클릭
5. 인증되면 **Sitemaps** 메뉴에서 `sitemap.xml` 제출

> ⚠️ `github.io` 주소는 DNS(도메인) 인증을 못 써요. GitHub 소유라 DNS에 접근할 수 없거든요. 반드시 **URL 접두어 + HTML 파일** 방식으로 하세요.

### 네이버 — 서치어드바이저

1. [네이버 서치어드바이저](https://searchadvisor.naver.com/) 접속
2. 사이트 등록 → **HTML 파일 업로드** 인증
3. 인증 파일을 저장소 루트에 올리고 커밋 → "소유확인"
4. **요청 → 사이트맵 제출**에 `sitemap.xml`, RSS에 `feed.xml` 등록

네이버는 등록해도 실제 검색에 뜨기까지 며칠~2주 걸리니 느긋하게 기다리면 됩니다.

## 마무리

처음엔 "이 파일이 왜 여기 있지?" 싶지만, 한 번 구조를 파악하면 글 쓰는 데만 집중할 수 있어요.
다음 글에서는 제가 실제로 겪은 커스터마이징 삽질들을 더 자세히 풀어볼 생각입니다.
