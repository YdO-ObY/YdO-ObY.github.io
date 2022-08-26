---
title: "[GitHub Pages] Jekyll 설치 방법"
date: 2022-08-16 23:19:15 +0900
categories: [GitHub, GitHub Pages]
tags: [github pages, jekyll]
---
<hr>
저번에는 GitHub Pages를 이용하여 블로그를 생성을 해보았다.

이번에는 Jekyll를 이용하여 홈페이지를 꾸며볼것이다.

## Jekyll이란 무엇인가? 
여기서 잠깐!

Jekyll에 대해 좀 알아보고 넘어가보고자 한다.

    Jekyll이란?
    
    어원은 Jekyll & Hyde의 Jekyll이다.

    GitHub설립자 중 한명이 Ruby를 기반으로 개발된 프레임워크.

    정적 웹사이트 구조이다.
    - 정적 웹사이트란
      저장된 파일만을 이용하여 사용자에게 띄워주는 방식
      Back-end코드가 없어 제작 간편
      속도가 빠르며 가벼움

    HTML, MarkDown등 Markup 언어를 이용하여 작성하면 규칙에 따라 웹 페이지 생성

이정도 까지만 알고 넘어가자

더 많은 정보를 알고싶다면 [Jekyll 지킬이란?](https://cheershennah.tistory.com/214) 여기로 넘어가서 보거나, 구글링을 통하여 공부를 해보자

<br>



## Ruby 설치

* 필자는 M1 MAC을 사용하고있으므로 brew로 설치를 진행한다

---


Jekyll을 설치하기전에 먼저 설치해야하는것이 있다.

무엇일까?

맞다. Ruby를 먼저 설치를 해야한다. 왜? Ruby기반으로 개발된 프레임워크니까

아래 명령어를 터미널에 입력하여 rbenv와 ruby-build를 설치한다.

    brew install rbenv ruby-build

`rbenv`
<br>
Ruby 버전 관리 패키지이다. Ruby의 여러버전을 설치 할 수 있으며, 사용할 버전을 선택하고 사용가능하다.

<!-- 자세한 설명은 [여기](https://github.com/rbenv/rbenv)를 참고 -->

<br>

`ruby-build`
<br>
다른 버전의 Ruby를 임의의 디렉터리에 컴파일하고 설치할 수 있게 하는 rbenv의 플러그인이다..
<br>
ruby-build는 rbenv 없이 독자적으로 사용 할 수도 있다.
<br>
macOS, Linux나 다른 UNIX-계열 운영체제에서만 사용 가능


<!-- 자세한 설명은 [여기](https://github.com/rbenv/ruby-build)를 참고 -->

자세한 설명은 [Ruby 공식 문서](https://www.ruby-lang.org/ko/documentation/installation/#ruby-build)를 참고


<br>

<hr>


    rbenv versions

현재 사용중인, 설치된 Ruby 버전을 확인 하는 명령어

![image](https://user-images.githubusercontent.com/69522086/184166343-d3320ea9-214f-485e-b0fb-f4d06bbbd738.png)

지금은 아무 버전도 설치한 상황이 아니라 system만 존재한다.

syetem 앞의 *는 현재 사용중 버전을 알려주는 표시이다.

<br><hr>

    rbenv install -l

설치 가능한 Ruby 버전을 보여주는 명령어

![image](https://user-images.githubusercontent.com/69522086/184167782-ae4046bb-0575-43b9-9bb5-a689a2227990.png)

<br><hr>

    rbenv install 원하는버전

필자는 2.7.6 버전을 사용할 것이다.

왜냐? 최신 버전으로 설치를 하는 경우 호환성 문제로 고생을 해본적이 너무 많아서 최신 버전을 약간 기피하는 성향이 생겼다.

최신버전 문서를 읽고나서도 왠지 모르는 불안감에 일단 구버전으로 설치한다.


![image](https://user-images.githubusercontent.com/69522086/184170628-d79871ef-ba67-4d57-bbf2-db938ae9abbe.png)
 

![image](https://user-images.githubusercontent.com/69522086/184170720-a7c13dfd-6b81-4097-ad29-94e026bf9921.png)


설치를 진행 완료 후 versions 명령어를 사용하여 2.7.6 버전이 설치가 된 것을 확인한다

---

    rbenv global 설치한 버전


![image](https://user-images.githubusercontent.com/69522086/184171634-01e01f4f-4d25-4448-8569-1ec4a0c29104.png)

# Bundler 설치

Bundler를 설치 하기전에 개념을 한번 살펴보고 가자

`Gem`
<br>
Ruby의 라이브러리 패키지
<br>
command line으로 명령을 사용가능

`Bundler`
<br>
필요한 gem과 gem의 버전을 설치, 추적하고  Ruby프로젝트를 제공하는 도구

<br>

이제 Bundler를 설치 해보자!

    gem install bundler

![image](https://user-images.githubusercontent.com/69522086/184495256-b57a680a-a643-4956-b059-20e80cd389e9.png)

해당 문구가 뜰것이다.

이것의 원인을 찾아보앗더니 처음에 2.7.6버전을 설치를 하였으나 아직까지 system Ruby버전을 사용하고 있는중이라 권한이 없어서 발생하는 에러라고 한다.

터미널 설정을 바꾸어 Ruby권한을 바꾸어야한다.

<hr>

## rbenv의 PATH 설정 추가
    vi ~/.zshrc

vi를 이용하여 .zsh 설정 파일을 연다.

    export PATH={$Home}/.rbenv/bin:$PATH && \
    eval "$(rbenv init -)"

PATH 설정 추가를 하고 저장을 한다.

    source ~/.zshrc

source 명령어를 사용하여 변경 설정을 적용을 한다.

<hr>

이제 다시 Bundler를 설치를 진행하면 bundler 설치는 끝이다.

![image](https://user-images.githubusercontent.com/69522086/184495708-207b87c5-670f-4508-a095-930a4d84543f.png)



# Jekyll 설치

    gem install jekyll

![image](https://user-images.githubusercontent.com/69522086/184543897-ba407d20-fd58-4f0c-8cf9-a06347bbd0f3.png)

jekyll 설치하는 도중 에러가 발생하였다.

Xcode업데이트 이후 Command Line Tools를 설치를 해야한다고 한다.

Command Line Tools를 설치하기 위하여 아래 명령어를 입력을 해봄

    xcode-select -install

명령어를 실행하였으나, 오류를 다시 마주하게 되었다.

![image](https://user-images.githubusercontent.com/69522086/184542456-727afca2-ac9e-49b7-be1b-da8dda6b28ba.png)

프로그램 업데이트를 해야하는데 찾아보니그냥 재설치를 많이 하는것 같아 따라해봄

    sudo rm -rf /Library/Developer/CommandLineTools

삭제후 다시 설치 명령어를 이용하여 설치 후, jekyll 설치하면 설치가 된다.

설치 완료후 jekyll 생성을해보자

# Jekyll 생성

처음에 clone한 위치로 가서 jekyll을 생성한다.

    jekyll new ./

명령어를 실행하기전에 전에 만들어둔 index.html을 삭제하고 실행하여야한다.

![image](https://user-images.githubusercontent.com/69522086/184544285-5e945628-2716-4606-8c70-6c37d7f5fa73.png)

안그러면 이런식으로 오류가 발생한다.

jekyll을 생성하게 되면 많은 파일들이 생성이 되는데 이파일들은 jekyll 기본 파일들이라고 생각하자

# Bundle 설치
jekyll과 마찬가지로 프로젝트 디렉토리 안에서 bundler를 설치해야한다.

    bundler install

# Local 서버 열기

    bundle exec jekyll serve

명령어를 이용하여 로컬서버를 열고 [localhost:4000](localhost:4000)으로 이동하여 서버가 열렸는지 확인!




이런식으로 로컬서버로 열리는것을 확인 할 수있다.

![image](https://user-images.githubusercontent.com/69522086/184544866-abbf4579-e317-4853-8093-6bc91a70200f.png)

<hr>

이번에 Jekyll 테마를 가져와서 꾸며보고 싶엇는데 Jekyll설치하는게 너무 오랜시간을 쏟아부어 테마 적용은 다음장에서 진행해야겟다.