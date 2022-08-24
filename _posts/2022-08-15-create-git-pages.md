---
title: "[GitHub Pages] GitHub Pages를 이용하여 블로그 개설하기"
date: 2022-08-15 22:41:30 +0900
categories: [GitHub, GitHub Pages]
tags: [github, github pages]
---

<hr>
이제부터라도 기록을 남기면서 생활을 해보고자 블로그를 하려고 한다.

Naver Blog, Notion을 생각을 하였지만...

단순히 그냥 난 개발자니까.. 속으로 생각하며 Git Blog를 생성 해보려한다.

<br>
<br>

## Github Repository를 생성한다.
![image](https://user-images.githubusercontent.com/69522086/183098208-ef6d1ae9-6100-4157-b819-4cbfc1c2d771.png)

Repository 이름을 깃허브 username.github.io로 생성한다.

필자는 아래의 설정을 따로 건들지 않고 빈 Repository를 만들기 위하여 설정을 아무것도 건들지 않았다.

README.md 파일은 나중에 테마를 적용할때 테마 프로젝트안에 README.md 파일이 존재하므로 따로 추가 하지 않았다.

<br>

## Repository를 clone 하기

생성한 Repository를 들어가서 Code를 주소를 복사한다.

아래 빨간 박스를 누르면 복사가 자동으로 된다.

![image](https://user-images.githubusercontent.com/69522086/183252758-74f7b0c8-8462-4424-9137-459e06acfc43.png)

복사된 주소를 터미널에서 저장하고 싶은 경로로 이동하여 아래의 명령어를 실행한다.

    git clone (복사된 주소)

## index.html 생성하기

Repository를 복사한 디렉토리에 가서 index.html 파일을 생성한다.

index.html의 역할은 홈페이지를 접속하였을때 기본적으로 보여주는 파일이다.

index.html파일을 생성하기 전에 브라우저를 열고 Repository명을 입력하고 접속해보자.

지금 만들고자 하는 블로그의 주소가 Repository명이다.

    https://ydo-oby.github.io/


홈페이지에 접속하게 되면 아래의 사진럼 404 Not found 오류를 보게 될것이다.

![image](https://user-images.githubusercontent.com/69522086/183296130-de945040-c459-4ae8-85c1-5e577fd8edf3.png)

너의 사이트에 현재 index.html 파일을 제공해줄것을 요청하고 있다.

이것을 다시 말하자면 

    "너의 사이트에는 지금 기본적으로 보여줄게 없어! 그래서 난 404 Error를 보여준거야!"

이것을 보면서 내가 위에서 말한 index.html의 역할을 다시 생각해보길 바란다.

이제 진짜로 index.html을 생성해보자!

터미널 명령어가 편하다면 터미널 명령어로 생성하고, 아니면 그냥 내가 clone한 폴더를 찾아서 index.html파일을 생성해준다.

생성을 해주었다면 이제 git에 파일을 올려준다.

    git add .
    git commit -m "create index.html"
    git push origin master
    
    or

    git add .
    git commit -m "create index.html"
    git push origin main

그리고 나서 내 git에 들어가서 index.html이 잘 넣어졌는지 확인하고 다시 주소창에 내 블로그로 들어가서 확인 해보자

![image](https://user-images.githubusercontent.com/69522086/183297436-319acac8-750e-4d3a-9780-7bd1deb0d0cf.png)

오류는 사라지고 흰색 화면만 나올것이다.

이상하게 생각하지 마라.

index.html은 존재하나 내용물이없어서 보여줄게 없어서 그런것이므로 정상적인것이다.

이렇게 일단 블로그는 생성이 되었다.

여기서 html 문법을 이용하거나 아무 글이나 작성하고 다시 git에 배포해보면 글이 작성이 되는것을 확인할 수 있다.

궁금하다면 이건 알아서 작성해보고 배포해보고 확인해보자.

Ruby, Jekyll을 이용해서 로컬서버 연결을 해볼것이다.

    Ruby는 무엇이지?

    Jekyll이 무엇인가?

    뭘까.. 궁금하다.