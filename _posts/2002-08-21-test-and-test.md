---
title: TITLE
date: 2002-08-21 23:41:30 +0800
categories: [TEST,TEST2]
tags: [TEST]
---

이번에는 Chirpy Thema 구성파악을 해보려한다.


## 구성파악하기

프로젝트 디렉토리를 열거나 터미널에서 ls 명령어를 사용하여 프로젝트에 무엇이 들어있는지 확인 해본다.

    _data _includes _javascript _layouts _plugins _posts _sass _site _tabs assets tools

현재 Chirpy를 구성하는 소스들을 종류별로 모아 놓은 것이다.
환경설정과 커스텀마이징을 위하여 소스 기능들을 설명하려 한다.



## Front Matter

Basically, you need to fill the [Front Matter](https://jekyllrb.com/docs/front-matter/) as below at the top of the post:

```yaml
---
title: TITLE
date: YYYY-MM-DD HH:MM:SS +/-TTTT
categories: [TOP_CATEGORIE, SUB_CATEGORIE]
tags: [TAG]     # TAG names should always be lowercase
---
```

> The posts' _layout_ has been set to `post` by default, so there is no need to add the variable _layout_ in the Front Matter block.
{: .prompt-tip }

### Timezone of Date

In order to accurately record the release date of a post, you should not only set up the `timezone` of `_config.yml`{: .filepath} but also provide the post's timezone in variable `date` of its Front Matter block. Format: `+/-TTTT`, e.g. `+0800`.

### Categories and Tags

The `categories` of each post are designed to contain up to two elements, and the number of elements in `tags` can be zero to infinity. For instance:

```yaml
---
categories: [Animal, Insect]
tags: [bee]
---
```
