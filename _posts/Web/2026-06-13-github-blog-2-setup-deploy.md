---
title: "[GitHub Blog #2] 로컬 환경 세팅 & 첫 배포"
excerpt: "Ruby 설치부터 git 기초까지, 터미널이 처음이어도 따라 할 수 있게 차근차근. 끝나면 인터넷에 내 블로그가 떠 있습니다."
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

> 📚 **GitHub 블로그 만들기 시리즈 #2** · [전체 목차](/web/github-blog-0-series-index/) · 이전: [#1 큰 그림](/web/github-blog-1-overview/) · 다음: [#3 첫 글 쓰기](/web/github-blog-3-first-post/)

이번 편의 목표.
> ✅ **빈 블로그를 인터넷에 띄운다.**

이 편은 시리즈에서 제일 길고, 솔직히 제일 까다로워요. 설치가 한 번에 안 되는 게 정상이니 너무 걱정 마세요.
**터미널을 처음 열어본다는 가정**으로 하나하나 적었습니다. 순서대로만 따라오시면 돼요.

> 💬 **터미널이 뭐예요?** 컴퓨터에 글자로 명령을 내리는 검은 창이에요.
> - **Mac**: `⌘ + 스페이스` → "터미널" 검색
> - **Windows**: 시작 → "PowerShell" 검색

---

## 1단계. GitHub 저장소 만들기

먼저 글과 코드가 살 집(저장소)을 만들어요.

1. [github.com](https://github.com) 로그인 → 우측 상단 **`+` → New repository**
2. **Repository name**에 반드시 **`내아이디.github.io`** 입력
   - 예: 아이디가 `iamlmj720`이면 → `iamlmj720.github.io`
   - ⚠️ 이 이름 규칙을 어기면 블로그로 안 떠요.
3. **Public** 선택 → **Create repository**

## 2단계. 테마(minimal-mistakes) 가져오기

밑바닥부터 만들면 너무 힘드니, 잘 만들어진 테마를 통째로 복사해서 시작해요.

1. [minimal-mistakes starter](https://github.com/mmistakes/mm-github-pages-starter) 접속
2. 초록색 **`Use this template` → Create a new repository**
3. 저장소 이름을 1단계와 똑같이 **`내아이디.github.io`** 로
   *(1단계에서 빈 저장소를 이미 만들었다면, 이 템플릿 방식으로 새로 만들고 빈 저장소는 지워도 돼요.)*

이러면 블로그에 필요한 파일이 전부 내 저장소에 복사됩니다.

## 3단계. 내 컴퓨터로 내려받기 (git clone)

> 💬 **git이 뭐예요?** 파일의 변경 이력을 저장하고, 내 컴퓨터 ↔ GitHub 사이를 오가게 해주는 도구예요. Mac엔 보통 깔려 있고, Windows는 [git-scm.com](https://git-scm.com)에서 설치하세요.

터미널에서 (`<>` 부분은 본인 걸로 바꿔서):

```bash
git clone https://github.com/<내아이디>/<내아이디>.github.io.git
cd <내아이디>.github.io
```

`cd`는 그 폴더 안으로 들어가는 명령이에요. 이제 이 폴더에서 작업합니다.

## 4단계. Ruby 설치 (제일 중요 ⚠️)

Jekyll은 Ruby라는 언어로 돌아가서, Ruby를 먼저 깔아야 해요. **여기서 막히는 사람이 제일 많아요.** OS별로 다릅니다.

### 🍎 Mac

Mac 기본 Ruby는 버전이 낮아 문제가 생기니, **rbenv로 새 Ruby**를 깝니다.

```bash
# 1) Homebrew 설치 (이미 있으면 건너뛰기)
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"

# 2) rbenv 설치
brew install rbenv ruby-build

# 3) rbenv 초기화 (안내 문구대로 ~/.zshrc에 추가 후 터미널 재시작)
rbenv init

# 4) 최신 Ruby 설치 & 기본으로 지정
rbenv install 3.3.0
rbenv global 3.3.0

# 5) 확인 (3.3.0이 나오면 성공)
ruby -v
```

### 🪟 Windows

[RubyInstaller](https://rubyinstaller.org/downloads/) 에서 **"Ruby+Devkit"** 버전(예: 3.3.x)을 받아 설치해요.

1. 설치 마지막 화면에서 **"Run 'ridk install'"** 체크 → 콘솔이 뜨면 그냥 **Enter**
2. 새 PowerShell을 열고 확인:
   ```powershell
   ruby -v
   ```

## 5단계. Jekyll 실행하기

Ruby가 준비됐으면, 블로그를 돌립니다. (3단계에서 들어간 폴더 안에서)

```bash
# 1) 필요한 도구 설치
gem install bundler

# 2) 이 블로그가 쓰는 패키지들 한 번에 설치
bundle install

# 3) 블로그 실행
bundle exec jekyll serve
```

성공하면 터미널에 `Server address: http://127.0.0.1:4000` 같은 줄이 떠요.
브라우저에서 **`http://localhost:4000`** 으로 들어가면 — 🎉 내 블로그가 보입니다!

> 글을 고치고 저장하면 대부분 자동 새로고침돼요. 단 **`_config.yml`을 고쳤을 땐 서버를 껐다(`Ctrl+C`) 다시 켜야** 반영됩니다.

## 6단계. 인터넷에 올리기 (배포)

로컬에서 잘 보이면, GitHub에 올려 진짜 인터넷에 띄워요.

```bash
git add .                       # 바뀐 파일 전부 담기
git commit -m "first commit"    # 저장 (메시지 붙여서)
git push                        # GitHub로 올리기
```

> 💬 세 명령의 뜻: **add**(담기) → **commit**(도장 찍어 저장) → **push**(GitHub로 보내기). 앞으로 글을 쓸 때마다 이 3단계를 반복해요.

push가 끝나고 1~2분 뒤, **`https://내아이디.github.io`** 로 접속하면 블로그가 떠 있어요.
저장소 **Settings → Pages**에서 배포 상태와 주소를 확인할 수 있습니다.

---

## 자주 나는 에러 해결 🚑

| 증상 | 원인 / 해결 |
|---|---|
| `requires ruby version >= 3.x` | Ruby가 낮음 → 4단계로 최신 Ruby 설치 |
| `command not found: jekyll` | `bundle exec`를 빼먹음 → `bundle exec jekyll serve` |
| `bundle: command not found` | `gem install bundler` 먼저 실행 |
| `Address already in use` | 4000 포트 사용 중 → 기존 서버 끄거나 `jekyll serve -P 4001` |
| push할 때 로그인 요구 | 비밀번호 대신 **GitHub 토큰** 또는 SSH 키 필요 (GitHub 문서 참고) |
| 배포는 됐는데 화면이 깨짐 | `_config.yml`의 `url` 값이 내 주소와 맞는지 확인 |

> 💡 에러 메시지는 무섭게 생겼지만, **그 문구를 그대로 구글에 검색**하면 십중팔구 똑같이 겪은 사람의 해결법이 나와요. 저도 그렇게 다 넘겼습니다.

## 다음 편

빈 집이 인터넷에 생겼어요. 이제 첫 가구를 들일 차례예요.
**[#3 첫 글 쓰기](/web/github-blog-3-first-post/)** 에서 글 하나를 발행해봅니다.
