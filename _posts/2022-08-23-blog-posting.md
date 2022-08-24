---
title: "[GitHub Pages] 블로그에 포스팅 하는 방법"
date: 2022-08-22 23:41:30 +0800
categories: [GitHub, GitHub Pages]
tags: [github pages, jekyll, chripy]
---

<hr>

블로그도 잘 만들어졌겟다. <br> 이제 글을 작성하는법을 알아보려한다.

[공식 문서](https://chirphy22.netlify.app/posts/write-a-new-post/)에 설명이 잘 되어있지만 정리 할겸 포스팅은 남겨본다.


## 파일생성

`_post`안에 파일을 생성해야하며, 파일 이름은 `YYYY-MM-DD-TITLE.md`형식으로 생성을 해주어야한다.

공백이 존재하면 안된다.

    ex)
    2022-01-01-first-blog-post.md


파일을 생성하고 로컬서버에서 확인하면 글이 작성 된것을 확인 할수있다.

![image](https://user-images.githubusercontent.com/69522086/186113061-79d73bee-196c-4a5f-b2d3-feee00608637.png)

<hr>

## 머리말 양식

머리말을 추가하여 제목, 작성날짜, 카테고리, 태그를 추가할 수 있다.

``` md
---
title: Title
date: YYYY-MM-DD HH:MM:SS +/- TTTT
categories: [Category1, Category2]      # 최대 2개까지 가능
tags: [tag1, tag2]                      # 제한없음, 소문자로 작성 
authors: username                       # _config.yml의 social.name 설정시 필요없음
---
```
{: .nolineno }

    ex)
    title: 블로그 첫 포스팅
    date: 2022-08-23 11:11:11 +0900
    categories: [GitPages, Jekyll]
    tags: [tag1, tag2]





## 목차

게시물의 오른쪽에 보이는 것이다.

스크롤에 위치에 따라 현재 위치를 보여준다.

![image](https://user-images.githubusercontent.com/69522086/186120820-cd412e09-8e1e-404e-b6ec-2934b499e4c0.png)

### 목차생성 방법


    ## 목차

    ### 하위 목차명
    
이렇게 생성할수있다.

하나의 목차에 하위 목차가 여러개 존재할 수 있다.


### 목차 설정
목차를 on/off가 가능하다.

#### 전역 설정
`_config.yml`파일의 `toc`을 `false`로 변경하면 모든 게시물에 목차가 안보이게 된다.


#### 특정 게시물 설정

```md
---
toc: false                              # default: true
---
```
{: .nolineno }


<hr>

`주의사항`

`## 1.목차` 처럼 목차 이름이 숫자로 시작하게되면 목차가 안먹힌다.
<hr>





## 게시물 고정

목록에서 게시물을 고정할때 사용

고정 게시물이 하나 이상일때 시간의 역순으로 정렬된다.

### 사용법

```md
---
pin: true
---
```
{: .nolineno }