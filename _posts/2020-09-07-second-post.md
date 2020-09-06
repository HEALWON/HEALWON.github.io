---
layout: post
title: "[github] Github blog(2): Memoirs jekyll theme customizing"
author: healwon
image: assets/images/스크린샷, 2020-08-30 17-51-48.png
categories: [github]
tags:
- blog
- jekyll

toc: true
published: false
---

개강하니까 하라는 공부는 안하고 글이 쓰고 싶어지는 신기한 현상. 이번에 내 수준에 들을만한 강의를 찾기가 정말 힘들었다... 지금의 내 수준에 대한 고찰을 하는 계기가 되었다. 이제부터라도 분야를 확실히 정하고 차근차근 프로젝트를 진행해 나가야지.  
저번 포스팅에서는 블로그 페이지를 만들고 jekyll 테마 적용, 로컬 작업 환경 만들기까지 진행했다. 여기서는 다분히 개인적인 customizing 과정을 정리해보았다. 본인은 markdown, html,css 등에 대한 배경지식이 없는 채로 눈치로 수정했다.  
밑의 내용은 같은 theme를 사용하지 않는 이상 별로 도움이 되지는 않겠지만... 이렇게까지 자세하게 쓰는 이유는 기록용이라고 생각해주시길 바란다. 혹시 조금이라도 겹치는 부분이 있다면 도움이 되시길 바란다.

### 1. _config.yml 내용 수정하기
***

### 2. Navigation Bar customizing
***

### 3. layout 제작하기
***

### 4. 기타 html, css 파일 수정하기
***

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
