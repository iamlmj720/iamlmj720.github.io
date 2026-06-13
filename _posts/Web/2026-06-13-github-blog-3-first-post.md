---
title: "[GitHub Blog #3] 첫 글 쓰기 - front matter와 마크다운"
excerpt: "_posts 규칙과 front matter를 이해하고, 이미지까지 넣은 첫 글을 발행합니다."
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

> 📚 **GitHub 블로그 만들기 시리즈 #3** · [전체 목차](/web/github-blog-0-series-index/) · 이전: [#2 환경 세팅](/web/github-blog-2-setup-deploy/) · 다음: [#4 카테고리 구성](/web/github-blog-4-categories/)

이번 편의 목표.
> ✅ **내 첫 글을 블로그에 올린다.**

## 1. 글 파일 규칙

글은 **`_posts` 폴더**에 넣고, 파일명은 반드시 이 형식을 지켜야 해요.

```
YYYY-MM-DD-제목.md
예) 2026-06-13-my-first-post.md
```

- 앞의 **날짜**는 글의 발행일이자 정렬 기준이에요.
- 뒤의 **제목 부분**이 URL(주소)에 들어갑니다. 한글보다 영문/하이픈을 추천해요.

## 2. front matter 뜯어보기

파일 맨 위 `---` 사이를 **front matter**라고 하고, 글의 설정값이 들어가요.

```yaml
---
title: "내 첫 글"          # 글 제목
excerpt: "한 줄 요약"       # 목록·검색에 보이는 설명
categories:
  - Web                   # 어떤 카테고리에 넣을지
tags:
  - GitHub                # 태그 (여러 개 가능)
date: 2026-06-13          # 발행일
toc: true                 # 글 안에 목차 표시
toc_sticky: true          # 스크롤해도 목차 따라오기
published: true           # false면 발행 안 됨(숨김)
---
```

| 항목 | 하는 일 |
|---|---|
| `title` | 글 제목 (화면 상단·탭) |
| `categories` | 카테고리 페이지에 자동 분류 |
| `tags` | 주제 태그 (분류 보조) |
| `excerpt` | 글 목록과 검색 결과의 한 줄 설명 |
| `toc` | 본문 옆 목차 on/off |
| `published` | `false`면 임시 숨김 |

## 3. 마크다운 기본

front matter 아래부터는 **마크다운**으로 본문을 씁니다.

```markdown
## 제목
### 소제목

- 목록 1
- 목록 2

> 인용문

**굵게**, *기울임*, `코드`

[링크](https://example.com)
```

> 💡 코드 블록 안에 `{{ ... }}` 같은 Jekyll 문법을 그대로 보여주고 싶다면 `{% raw %}` … `{% endraw %}`로 감싸야 해요. 안 그러면 Jekyll이 그걸 실제 코드로 해석해버립니다.

## 4. 이미지 넣기

이미지는 보통 `assets/img/` 같은 폴더에 넣고, 아래처럼 불러와요.

{% raw %}
```markdown
<img src="{{ '/assets/img/posts/example.jpeg' | relative_url }}" alt="설명" />
```
{% endraw %}

`relative_url`을 쓰면 로컬에서나 배포된 사이트에서나 경로가 안 깨져요.

## 5. 발행하기

글 파일을 만들고 `git push` 하면 끝이에요. 1~2분 뒤 블로그에 글이 올라옵니다.
아직 발행하기 이르면 front matter에 `published: false`를 넣거나, `_drafts` 폴더에 두면 숨길 수 있어요.

## 다음 편

글이 하나둘 쌓이면 분류가 필요해져요.
**[#4 카테고리·태그·사이드바 구성](/web/github-blog-4-categories/)** 에서 글을 정리하는 법을 다룹니다.
