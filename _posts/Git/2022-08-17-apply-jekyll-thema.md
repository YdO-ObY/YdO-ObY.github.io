---
title: "[GitHub Pages] Jekyll Thema 적용방법"
date: 2022-08-17 22:56:32 +0900
categories: [GitHub, GitHub Pages]
tags: [github pages, jekyll]
---

<hr>

저번에는 Jekyll 로컬 서버를 이용하여 로컬에서 어떻게 띄우는 알아보았다.

이번에는 Jekyll 테마를 적용하여 블로그를 꾸며볼것이다.

## Jekyll 테마 선택하기

찾아보니 Jekyll 테마가 엄청 많다.

테마를 모아둔 사이트를 소개하려한다.

* [jamstackthemes.dev](https://jamstackthemes.dev/ssg/jekyll/)
* [jekyllthemes.org](http://jekyllthemes.org)

여기 두개가 제일 보기 쉬워보여 두가지만 적어 놓았다.

위의 사이트를 하나하나 보면서 원하는 테마를 찾는것도 좋지만, 많이 사용하는 테마들이 정보도 얻기 쉽고 그래서 테마 사용 순위를 한번 찾아보았다.


[Free Jekyll themes for 2022](https://cloudcannon.com/blog/free-jekyll-themes-for-2022/##keyword:jekyll) << 2022년 3월 기준 사용 용도별 순위가 포스트된 사이트가 있어 여기도 소개 해보았다.


필자는 chirpy 테마를 사용하였다. 원래는 주변에서 minimal-mistakes를 많이 사용하길래 따라하려했으나, 여러 사이트를 소개하려고 찾다보니 chirpy가 깔끔해보여 선택했다.

<br>

## 테마 다운받기

`테마를 다운받는 방법은 2가지로 나뉜다.`

### a. 프로젝트를 ZIP으로 받는 방법
`repo를 미리 만들어 놓고 프로젝트 파일을 넣는 방식`

### b. 프로젝트를 Fork하는 방법
`repo를 미리 만들지 않고 다른사람의 repo를 복제하는 방식`

<span style="color:red">필자는 a방식을 사용하여 진행 할것이다.</span>

왜냐하면, 이미 앞장에서 repo를 만들고 진행을 했기도 했고

fork방식은 chripy thema 개발에 관여를 하지않을거면 추천하지않는다고 적혀있다.[자세한 설명](https://chirpy.cotes.page/posts/getting-started/)은 여기서 확인 가능

다른테마도 똑같이 진행해주되 테마마다 fork를 지향하는지 지양하는지 확인하고 a,b방식을 선택하여 진행하길 바란다.

테마를 선택하였다면, 해당 테마 github repo를 접속하여 다운로드 한다.

필자와 같은 테마를 이용한다면 [Chripy Thema 다운로드](https://github.com/cotes2020/jekyll-theme-chirpy/releases)에 접속하여 진행하면 된다.

![image](https://user-images.githubusercontent.com/69522086/185933716-2cb517fa-3489-4a8b-8e44-0d9801846e28.png)

릴리즈 버전이 여러가지 있는데 최신버전으로 Download ZIP을 클릭하여 파일을 다운로드한다.

<hr>

## 테마 적용하기

이전에 작성햇던 

ZIP파일을 압축 해제하고 모든파일들을 프로젝트안으로 가져온다.

`주의사항`

    압축풀때 모든 파일(숨김파일포함)을 다 가져와야한다.

    초기화 진행할때 진행이 안되는 경우 발생함.

여러 정보를 찾아보던중 Chripy테마는 파일을 가져온후 초기화를 진행해줘야한다는것을 알아냇다.

### 초기화 방법

프로젝트를 가져온 상태에서 commit을 진행한다.

    git add .

    git commit -m "Init Chripy Thema"

그리고 Chirpy Thema는 shell 명령어로 초기화를 진행할 수 있도록 sh파일을 제공한다.

    sh tools/init.sh

![image](https://user-images.githubusercontent.com/69522086/185934827-bbbc6b9d-9cca-4883-a87d-3c1241219d2c.png)

명령어를 통해 init.sh을 실행하면 아래 사진과 같이 초기화 성공 메세지 출력이 된다.

`init.sh 실행하면 무슨일이 일어나지??`

나중에 포스트해야겟다~


### Jekyll 실행하기

테마를 적용하였으니 확인 하기 위해 Jekyll을 실행하여 로컬에서 확인을 해보자!

앞에서 설정하였으니 Jekyll을 실행해보았다..

아앗... 여기서 문제가 발생하였다..

![image](https://user-images.githubusercontent.com/69522086/184661886-8f86bae1-6299-441c-a8ab-6b922ca8257b.png)

오류가 발생하는 이유는 테마에 적용할때 기존에 설치한 bundle이 삭제되어 bundle을 새로 설치해야 한다는것이다.

왜 다른 블로그에서 테마를 정해놓고 jekyll을 설치를 하는지 깨달아버렸다.

여러 시행착오 겪는거??

오히려 좋아

    bundle install

bundle 새로 설치하고

    bundle exec jekyll serve
    or
    sh tools/run.sh

`Chripy Thema는 로컬 서버를 여는 sh파일을 제공한다.`

로컬 서버 열린거 다시 확인하고 [localhost:4000](localhost:4000)로 다시 접속하면 테마가 적용된것을 확인 할 수있다.

![image](https://user-images.githubusercontent.com/69522086/185940662-cd18d9d8-f42f-4c36-aad0-c57b6bc82d1c.png)


## 기본 설정

테마를 적용하였으니 이제 기본설정을 건드려 보려한다.

기본설정은 `_config.yml`을 이용하여 수정한다.

기본 필수속성
* baseurl : 로컬 테스트용 `''` 
* url : 블로그 주소 `https://gitusername.github.io` 
* lang : 언어설정 `en` or `ko-KR`
* timezone : 표준시간 설정 `Asia/Seoul`

![image](https://user-images.githubusercontent.com/69522086/185958011-fcaaef1f-7733-4776-8fe7-a717a2f428bd.png)

사이드바 설정

* avatar : `이미지 링크`
* title :  `원하는 제목`
* tagline : `부제목 설정`
* github : `github_username`
* twitter : `tiwtter_username`
* email : `email_username@email`


처음으로 설정 해볼만한 것들은 이정도로 존재하며

`_config.yml`은 이 글만보고 파악하려하지말고 한번 열어서 글보면서 수정도 해보고 다 읽어보길 바란다.

많은 설정 부분이 존재하며 주석으로 설명도 잘되어있으니 추가적으로 설정할것이 있는지 확인 해보자

## 배포하기

설정을 바꾼것을 로컬에서 확인을 다하였으면 git에 배포를 하자.

배포하기전 .gitignore에 제외시켜야할 파일이 있다.

    echo "Gemfile.lock" >> .gitignore

명령어를 실행하여 Gemfile.lock을 제외시킨다.


    git add -A

    git commit -m "blog default setting"

    git push

## Git Pages branch 설정
git에 배포가 정상적으로 되었다고 해도 페이지에 접속하면 적용이 안되는것을 확인할 수 있다.

    --- layout: home # index page ---
  
이런 메시지만 출력될 것이다. 정상이다.

Github에서 push된 코드들을 빌드를 하여 `gh-pages` branch가 없으면 생성&배포하고 존재하면 해당 branch에 배포를 한다.

Gitpage 설정을 빌드된 branch로 해야한다.

![image](https://user-images.githubusercontent.com/69522086/186060518-bfdc4c0b-2378-44f2-ab76-45d6e4f65e84.png)

![image](https://user-images.githubusercontent.com/69522086/186061125-ff1bc509-9eec-4880-9692-88d3ef7e8e1f.png)

Github repo의 상단 탭에서 `Setting` 으로 들어가서 `master` branch를 `gh-pages`로 바꾸고 `Save`를 누르면 변경이 된다.

저장하고 바로는 적용이 안되고 한 3~5분정도 후에 블로그주소에 접속하여 보면 적용 된것을 확인 할수있다.

![image](https://user-images.githubusercontent.com/69522086/186062347-982a7b41-3200-4de6-a276-fadd4ad213e5.png)

위의 주소를 보면 로컬이 아닌 Github repo 주소인것을 확인하자


이것으로 테마 적용 및 기본 설정은 완료 했으며, 다음장에는 간단하게 테마 구성파악을 포스팅 하려한다.



<hr>

## <span style="color:red">오류발생</span>

테마 설정 하면서 발생한 오류들을 적어본다.

### Chirpy 초기화 실행 오류 1

ZIP을 해제하고 초기화를 진행하려는데 이런 오류가 발생하였다.

![image](https://user-images.githubusercontent.com/69522086/185962723-deb0ff6e-6bda-47cc-9976-f1b812468c7a.png)

    원인 :
    git 변동사항이 존재하여 발생하는 오류

    해결 :
    commit을 올리면 해결

<hr>

### Chirpy 초기화 실행 오류 2

`[INFO] Initialization successful!`출력이 안되고 `Already initialized.`만 출력이 되었었다.

    원인 :
    .github이 존재하지않아서 발생하는 오류
    ZIP압축 파일을 해제하고 복사해오면서 숨김파일을 안넣어서 생긴다.

    해결 :
    터미널에서 (Mac) ls -a , (Windows) dir /a 명령어를 통해 .github파일이 존재하는지 확인

    여기서 의문!
    왜 오류라고 안나오지? 라고 생각할 수 있다.
    이걸 이해하려면 init.sh 소스를 보면 된다.

```shell
check_init() {
  local _has_inited=false

  if [[ ! -d .github ]]; then # using option `--no-gh`
    _has_inited=true
  else
    if [[ -f .github/workflows/$ACTIONS_WORKFLOW ]]; then
      # on BSD, the `wc` could contains blank
      local _count="$(find .github/workflows/ -type f -name "*.yml" | wc -l)"
      if [[ ${_count//[[:blank:]]/} == 1 ]]; then
        _has_inited=true
      fi
    fi
  fi

  if $_has_inited; then
    echo "Already initialized."
    exit 0
  fi
}
```
    check_init() 부분에서 .github/workflows/을 찾아야하는데 존재하지않아서 그렇다.

<hr>

### 배포오류 1

    증상 :
    username.github.io에 접속하게되면 페이지가 안뜨고 git - repo - Actions에서 오류가 발생함

    원인 :
    .gitignore에 Gemfile.lock을 추가하지않고 배포하는경우
 

    해결 :
    웹으로 들어가 git repo에서 Gemfile.lock을 삭제하고 커밋을 올린다.

### 배포오류 2


    증상 :
    refusing to allow a Personal Access Token to create or update workflow `.github/workflows/pages-deploy.yml` without `workflow` scope
    git push 오류 발생

    원인 :
    git repo에서 workflows 권한이 없어 발생
 

    해결 :
    git account Setting - Developer settings - Personal access tokens - 기기에 적용된 key 클릭 - workflow 체크박스 클릭 - Update token
    설정이 끝나고 배포 재시도를 한다.
    (repo Setting이 아닌 account Setting)
    





