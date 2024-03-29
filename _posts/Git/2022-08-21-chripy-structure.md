---
title: "[GitHub Pages] Chirpy Thema 구성 파악"
date: 2022-08-21 23:31:15 +0900
categories: [GitHub, GitHub Pages]
tags: [github pages, jekyll, chripy]
---

<hr>

이번에는 Chirpy Thema 구성파악을 해보려한다.


프로젝트 디렉토리를 열거나 터미널에서 ls 명령어를 사용하여 프로젝트에 무엇이 들어있는지 확인 해본다.

    _data _includes _javascript _layouts _plugins _posts _sass _site _tabs assets tools

현재 Chirpy를 구성하는 소스들을 종류별로 모아 놓은 것이다.
환경설정과 커스텀마이징을 위하여 소스 기능들을 설명하려 한다.

## <span style="color:yellow">_data</span>
구성 요소 : 왼쪽 사이드의 버튼들을 구성하는 소스, 언어구성 소스 [yml]<br>
변경 요소 : 버튼 구성 변경, 언어 변경 등 수정가능

## <span style="color:yellow">_include</span>
구성 요소 : UI를 구성하는 소스 [html]<br>
변경 요소 : sidebar, topbar, footer 등등

## <span style="color:yellow">_javascript</span>
구성 요소 : UI의 기능 구현 소스 [js]<br>
변경 요소 : js를 잘 알지 못한다면, 수정하지 않는 것을 추천한다.


## <span style="color:yellow">_layouts</span>
구성 요소 : include와 마찬가지로 UI를 구성하는 소스[html]<br>
변경 요소 : 글양식, 태그, 카테고리 구성 등등

## <span style="color:yellow">_plugins</span>
구성 요소 : 사이트 생성에 필요한 ruby 소스[rb]<br>
변경 요소 : X

## <span style="color:yellow">_posts</span>
구성 요소 : 사용자가 업로드할 글들을 저장하는 곳<br>
변경 요소 : 글 작성할때마다 여기에 저장하면 알아서 적용

## <span style="color:yellow">_sass</span>
구성 요소 : UI의 디자인을 구성하는 소스 [scss]<br>
변경 요소 : 디자인 구성

## <span style="color:yellow">_site</span>
구성 요소 : 프로젝트를 빌드하면 생기는 작업물 자체, 로컬에서만 사용<br>
변경 요소 : 변경된 프로젝드가 빌드되면 변경, gitignore에 포함 되어있어 git에는 배포가 되지 않음.

## <span style="color:yellow">_tabs</span>
구성 요소 : 사이드 바의 메뉴들의 랜딩 페이지 표시 <br>
변경 요소 : 버튼 순서, 아이콘 변경 가능


## <span style="color:yellow">assets</span>
구성 요소 : 이미지 파일<br>
변경 요소 : 사용하고 싶은 이미지 파일 넣어놓고 사용

## <span style="color:yellow">tools</span>

앞에서 초기화랑 로컬서버실행할때 사용해보았다.

구성 요소 : 프로젝트 초기화, 배포, 릴리즈, jekyll 로컬 서버 열기 를 실행 해주는 shell 파일<br>
변경 요소 : 사용시 오류가 난다면 구글링해서 원인이 무엇인지 찾고 왠만하면 수정하지말자

일단 구성만 어떤식으로 되어있는지만 파악하고 자세하게는 나중에 구성을 바꾼다던가 하는마음이 생기면 그때 포스팅을 해야겠다.


다음에는 글쓰는 방법을 포스팅 하려한다.