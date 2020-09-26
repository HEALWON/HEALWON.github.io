---
layout: post
title: "[github] Github blog(2): Jekyll theme customizing"
author: healwon
image: assets/images/스크린샷, 2020-08-30 17-51-48.png
categories: [github]
tags:
- blog
- jekyll

toc: true
published: true
---

 개강하니까 하라는 공부는 안하고 글이 쓰고 싶어지는 신기한 현상. 이번에 내 수준에 들을만한 강의를 찾기가 정말 힘들었다... 지금의 내 수준에 대한 고찰을 하는 계기가 되었다. 이제부터라도 분야를 확실히 정하고 차근차근 프로젝트를 진행해 나가야지.  

 저번 포스팅에서는 블로그 페이지를 만들고 jekyll 테마 적용, 로컬 작업 환경 만들기까지 진행했다. 여기서는 다분히 개인적인 customizing 과정을 정리해보았다. 본인은 markdown, html,css 등에 대한 배경지식이 없는 채로 눈치로 수정했다.  

 <s>밑의 내용은 같은 theme를 사용하지 않는 이상 별로 도움이 되지는 않겠지만... 이렇게까지 자세하게 쓰는 이유는 기록용인 걸로. 혹시 조금이라도 겹치는 부분이 있다면 도움이 되시길 바란다.</s>
_config.yml파일 내용 수정 이외에는 간략하게 기록하였다. 이유는 아래 참조.


### 1. _config.yml 내용 수정하기
***

_config.yml은 블로그의 기본적인 정보를 저장하는 중요한 파일이다. 여기 적힌 내용을 기반으로 블로그 페이지가 생성될 것이다.  
이 블로그에서 사용한 memoirs 테마 기준으로, 기본적으로 수정해야 할 부분은 다음과 같다.  
```
# Site
name: "Memoirs"
title: "Memoirs"
description: "I will take you on the fabulous world of exploration. Travel, culture, lifestyle. Eat, Pray, Love!"
logo: 'assets/images/logo.png'
favicon: 'assets/images/logo.png'
baseurl: /jekyll-theme-memoirs
disqus: 'demowebsite'
email: wowthemesnet@gmail.com
```
 사이트의 핵심 정보를 담고있는 부분. name과 title을 변경하면 브라우저 상단의 페이지에 표시되는 부분도 바뀐다.  
주의할 부분은 **baseurl: ""** 로 세팅하기. 그 외에는 자신의 github 페이지의 설정을 넣어주면 될 듯 하다.  

**favicon**: 브라우저 상단에 표시되는 아이콘.  
**disqus**: 이 테마에서 제공되는 댓글은 disqus 서비스를 이용하는데, 입력한 이름의 사이트 댓글 활동 내역을 모아볼 수 있다. 본인의 블로그 이름으로 설정하였다.  
```
google_analytics: 'UA-xxxxxxxx-1'
mailchimp-list: 'https://wowthemes.us11.list-manage.com/subscribe/post?u=8aeb20a530e124561927d3bd8&amp;id=8c3d2d214b'
```
필요 없다고 판단하여 빼버렸다. 아직 검색엔진에 등록을 안한 관계로..
```
# Authors
authors:
  sal:
    name: Sal
    display_name: Sal
    gravatar: e56154546cf4be74e393c62d1ae9f9d4
    email: wowthemesnet@gmail.com
    web: https://www.wowthemes.net/donate/
    twitter: https://twitter.com/wowthemesnet
    description: "Author of Mediumish, a Bootstrap Medium styled template available for WordPress, HTML, Ghost and Jekyll. You are currently previewing Jekyll template demo."
  john:
    name: John
    display_name: John
    avatar: 'assets/images/avatar.png'
    gravatar: b1cc14991db7a456fcd761680bbc8f81
    email: wowthemesnet@gmail.com
    web: https://www.wowthemes.net
    twitter: https://twitter.com/wowthemesnet
    description: "This is the author box. Write a short description of the author here. You are currently previewing Mediumish demo, a Jekyll template compatible with Github pages."
```
글쓴이가 여러명일 경우를 위해, 이와 같이 글쓴이 정보를 따로 기재하는 기능이 있다. 여기서는 1명이므로 1명의 정보만 기재.  
```
# Pagination 
paginate: 6
paginate_path: /page:num/
``` 
한 페이지에 보여줄 포스트의 수.  
```
# Lazy Images ("enabled" or "disabled")
lazyimages: "disabled"
```
이미지 로딩이 안 될 때 기본 이미지를 띄우는 옵션. 안할 이유가 딱히 없어 "enabled"로 설정.  
```
# Post Author Box ("enabled" or "disabled")
authorbox: "disabled"
```
포스트 밑에 글쓴이 정보를 보여주는 옵션. 마찬가지 이유로 "enabled".  

기본적으로 꼭 필요하다고 생각하는 항목 이외에는 삭제하고 자기 블로그의 정보를 채워넣는다는 느낌으로 하였다.


### 2. 이후 커스터마이징 과정
***

 블로그에서 보이는 부분 몇가지를 바꾸는데 상당히 힘들었고, 시간도 오래 걸려 웬만하면 기록하려 했으나, 아무래도 과정이 너무 파편적이고 개인적이라 도움이 되지 않을 것 같았다.  
그래서 여기에 간략한 흐름만을 적어 놓기로 했다. 추후에 jekyll 테마 자체에 대한 내용을 따로 다루어 봐야겠다.


**1. Navigation Bar customizing**

![image7](/assets/images/스크린샷, 2020-08-30 17-55-12.png)  

![image1](/assets/images/스크린샷, 2020-08-30 17-51-48.png) ```네비게이션 바 수정 전후. 사진은 재탕```   

기본 네비게이션 바에 있는 memoirs 테마 관련 항목을 삭제하고 카테고리, 태그별 보기 항목을 추가하였다.  
네비게이션 내용을 수정하기 위해, _layout 폴더의 default.html을 수정해주었다. 다른 테마에 해당할지는 모르겠지만 해당 파일에 네비게이션 관련 내용이 들어있을 확률이 높을 것이다.


**2. layout 수정하기**

jekyll의 많은 테마에서 카테고리별 보기 기능을 한 페이지에 모든 글을 모아 보여주는 방식으로 하는 것 같은데, 이 방식으로는 원하는 글을 찾기가 힘들다고 느껴저 _layout 폴더에 해당 카테고리 혹은 태그의 게시글을 보여주는 .html 레이아웃을 만들었다.  
단점은 카테고리/태그가 생길 때마다 페이지를 따로 만들어주어야 한다는 것. 추후에 기능을 추가해야 할 듯 하다.


**3. 기타 html, css 파일 수정하기**

중요한 부분은 아니지만 게시물을 표시하는 포스트박스의 규격이 들쑥날쑥하여 정리를 해주었다.  
assets/css/theme.scss에서 필요한 class를 찾아 규격 등을 수정하였다.


### 5. 여담, 미래 수정 계획
***
이걸로 지금까지의 자잘한 customizing을 끝냈다. 로고는 아직 나만의 것이 존재하지 않아서 당분간은 그냥 두려 한다.  
 차후에 google 검색 노출, category/tag별 보기 등의 기능을 구현할 예정이다. 아직 Navigation Bar가 완벽하지 않고 404상태인 것도 있어 최대한 빨리 수정하고 싶지만 우선은 학업부터. 검색 노출은 홈페이지를 좀 더 보완하고 사이트의 아이덴티티를 확립한 후에 하고 싶다.  
 처음에 category/tag별 보기 기능의 형태로 현재 선택한 category와 tag에 해당하는 글이 밑에 나열되는, 일종의 filtering기능을 생각하였으나 다시 보니 jekyll은 '**정적** 사이트 생성기'였다. 본래 형태인 각 카테고리별 포스트를 모두 나열하는 건 페이지의 정보량이 너무 많다고 생각하기에 적절한 방법을 생각해봐야 할 것 같다.

### 6. References
***
기본적인 토대는 줌코딩님의 게시글을 참고하였다.   
[차근차근 Github 블로그 만들기(3) - Github 블로그 커스터마이즈하기
by 줌코딩](https://zoomkoding.github.io/gitblog/2019/08/18/git-blog-3.html)

_config.yml의 내용을 이해하는데 많은 도움을 받았다.  
[GitHub 블로그 기본 설정하기 - 취미로 코딩하는 개발자](https://devinlife.com/howto%20github%20pages/blog-config/)


-2020.09.07 글 초안 작성  
-2020.09.27 글 내용 추가, 공개
