---
layout: post
title: "[github] Github blog(1): repository 생성 ~ jekyll theme 적용하기"
author: healwon
image: assets/images/makeblog/스크린샷, 2020-08-30 17-51-48.png
categories: [github]
tags:
- blog
- jekyll

toc: true
---

### 1. github blog
***
개인 블로그를 사용하는 건 네이버 이후로 처음이다. 학부 3학년이 되었는데 정작 머리에 남은게 아무것도 없는 것 같아서, 필력도 기를 겸 공부 기록용으로 블로그를 만들어 사용해보려 한다. 주로 공부하다가 막힌 부분에 대해 쓰게 될 것 같다.   
아래에는 구글링해가며 찾은 블로그 제작 과정을 정리해보려 한다.

![image1](/assets/images/makeblog/스크린샷, 2020-08-30 17-51-48.png) ```완성한 블로그. 로고, 프로필 등은 차차 추가해 나가려 한다. (2020.08.30 기준)```

### 2. repository 생성하고 local 저장소 만들기
***
github page를 만들기 위해서는 page용 repository를 따로 만들어야 한다.   
[github](https://github.com/)으로 가서, (만일 계정이 없다면 만들어준 후) new를 눌러 새 repoaitory 설정 화면으로 이동한다.   
이때 repository 이름은 반드시 username으로 시작해야 하는데,   

![image2](/assets/images/makeblog/스크린샷, 2020-08-30 17-53-26.png)```special repository?```

이렇게 special repository를 작성할 수 있기 때문이라고 뜬다. blog를 만드려면 **'username.github.io'**를 입력해 주고, 공개로 설정한 뒤 'Add a README file'을 선택하여 초기 설정을 해 주었다.   

![image3](/assets/images/makeblog/스크린샷, 2020-08-30 17-52-30.png)

처음에는 *README.md* 파일만 존재할 것이다. 이제 편한 수정을 위해 컴퓨터에 local 저장소를 만들어주는데, 처음 만들 때에는 clone, 이후에는 push로 local->git, pull로 git->local 업데이트를 한다. 업데이트 되는 쪽은 데이터가 손실되니 local 파일을 수정하고 pull을 하는 등의 실수를 하지 않도록 주의해야겠다.   


***

#### 주의!   
본인은 노트북에 ubuntu, window 듀얼부팅을 설치하여 모든 과정을 ubuntu로 진행하였다. ubuntu의 경우 프로그램 설치, 명령어 실행 등을 terminal에서 편하게 할 수 있지만 window의 경우 과정이 다를 수 있다. (git bash?를 사용한다고 들었다.)   

***

![image4](/assets/images/makeblog/스크린샷, 2020-08-30 17-52-43.png)

ssh키를 만들지 않아 경고문이 뜨는데, 그냥 *clone with HTTPS*를 사용했다.   

![image5](/assets/images/makeblog/스크린샷, 2020-08-30 17-52-55.png)

위의 주소를 복사하고 terminal에 다음과 같이 입력했다.   
(git이 설치되어 있지 않을 경우 설치해야 한다.)
```terminal
$ cd dir (저장공간을 만들 폴더로 이동한다.)
$ git clone "복사한 주소"
```
여담으로, terminal은 ctrl-v가 안 먹히는데, 그냥 오른쪽 클릭하니 되더라...

이제 해당 폴더에 **'username.github.io'**라는 이름의 폴더가 생긴 것을 확인할 수 있다. *https://username.github.io*가 자신의 블로그 주소가 된다.

### 3. jekyll theme 적용하기
***
*3. jekyll theme 적용하기*와 *4. localhost 사용하기*는 ruby를 이용한다. ruby는 사용해 본 적이 없지만, 그냥 열심히 설치하다보니 어떻게든 되었다.

![image6](/assets/images/makeblog/스크린샷, 2020-08-30 16-24-23.png)

[jekylltheme.org](http://jekyllthemes.org/)에서 비상업/상업적 이용이 가능한 무료 블로그 테마를 제공하고 있다. 

>Jekyll is a simple, blog-aware, static site generator for personal, project, or organization sites. Written in Ruby by Tom Preston-Werner, GitHub's co-founder, it is distributed under the open source MIT license. <https://en.wikipedia.org/wiki/Jekyll_(software)>

원하는 테마를 찾아 다운받는데, 분류체계 등 자신이 사용하고 싶은 스타일과 비슷한 테마를 고르는 것을 추천한다. 내가 사용한 [Memoirs Jekyll Theme](http://jekyllthemes.org/themes/memoirs-jekyll-theme/)의 경우, category가 tag와 비슷한 역할을 하여 한 게시물이 여러 category에 속하기도 한다. 나중에 하위 category가 만들고 싶어지면 다 직접 만들어야 하는 셈이니, 굳이 일을 만들지 말고 처음부더 스타일을 잘 골라놓는 것이 좋아보인다. 본인은 직접 다뤄보고 싶기도 해서 중간에 바꾸지 않았다.

구글링하다보니 많은 분들이 사용하시는 테마가 있어 여기에 링크를 남긴다.   
[Minimal Mistakes](https://mmistakes.github.io/minimal-mistakes/)

다운받은 zip파일의 압축을 풀어, 내용물을 전부 복사하여 *username.github.io*폴더 내에 붙여넣기한다. README.md파일이 이미 존재한다고 뜨는데, 덮어써도 상관은 없다.

이 다음에 ruby 프로젝트를 사용할 때 의존성 문제가 나는 것을 막기 위해서 [bundler](https://ruby-korea.github.io/bundler-site/)를 설치해야 한다고 한다. terminal에 다음과 같이 입력해주면 되는데...
```terminal
$ gem install bundler
$ bundle install
```
본인은 ruby를 설치하지 않아서 ruby부터 설치했다. 대부분은 terminal에서 하라는 대로 했더니 됐던 것 같다.
ruby가 설치되었는지는 다음을 입력하여 확인한다. 버전이 뜨면 설치된 것이다.
```terminal
$ ruby -v
```

이제 terminal에 다음을 입력해 git에 업로드하면 테마가 적용된 것을 확인할 수 있다. 시간이 좀 걸린다.
```terminal
$ git add .
$ git commit -m "커밋 내용"
$ git push
```

### 4. localhost 사용하기
***
상술했듯이 push하고 적용되기까지는 시간이 좀 걸리는데, 이제 테마를 수정해야 하는데 확인하려니 시간이 너무 오래 걸린다. 그래서 local에서 수정한 사항을 하나하나 업로드하지 말고 바로바로 보기 위해 jekyll을 이용한다고 한다.

결론부터 말하자면 다음을 실행하면 되는데,
```terminal
$ cd .../username.github.io (local 저장소 폴더로 간다)
$ bundle exec jekyll serve

...
...
  Server running... press ctrl-c to stop. # 다음 문장이 뜨면 실행되고 있는 것이다.
```

이를 위해서는 jekyll bundler를 설치해주어야 한다.
```terminal
$ gem install jekyll bundler
```
줌코딩님의 게시글에는 이 한줄로 정리가 되었는데, 내가 하려 하니 오류가 계속 떠서 구글링하고 난리가 났다.   

***

**1. Permision error**

```terminal
$ gem install jekyll bundler

ERROR:  While executing gem ... (Gem::FilePermissionError)
    You don't have write permissions into the /usr/bin(다를 수 있음) directory.
```
이 오류는 의외로 간단하게 해결된 것이 앞에 sudo를 붙이니 해결됐다. 그러나... 

**2. Native Extension build fail (Nokogiri)**

```terminal
$ sudo gem install jekyll bundler

...
...
Building native extensions.  This could take a while...
ERROR:  Error installing nokogiri:
       ERROR: Failed to build gem native extension.

ruby extconf.rb --with-ldflags
```
이것과 비슷한 형태의 에러가 났다.  
(<https://stackoverflow.com/questions/2741129/installing-nokogiri-ruby-gem-with-a-native-extension>에서 인용)  
특히 nokogiri를 설치하는 과정에서 일어나는 것 같은데, terminal에서 하라는대로 해도 잘 안 되더라. 
헤매다가 [Nokogiri 공식 홈페이지](https://nokogiri.org/tutorials/installing_nokogiri.html)를 보고 해결했다. 공식 홈페이지부터 찾아봐야겠다는 교훈을 얻었다...
```terminal
$ sudo apt-get install build-essential patch ruby-dev zlib1g-dev liblzma-dev
$ gem install nokogiri
```
**주의!** zlib1g는 중간에 l이 아니라 숫자 1이다. 이것때문에 처음에 아닌 줄 알았다.  
```terminal
sudo apt-get install libxslt-dev libxml2-dev zlib1g-dev
sudo gem install nokogiri
```
다음과 같이 하는 방법도 있는듯 하다. 본인은 둘다 했더니 되었다.(<https://stackoverflow.com/questions/2741129/installing-nokogiri-ruby-gem-with-a-native-extension>에서 인용)  

중간에 결국 갈아엎었는데, 왜인지 모르게 local 저장소에 .bundle, vendor 폴더가 만들어져 있었다. 지금은 없는 걸 보니 그때 뭔가 잘못했었나 보다.

***

설치가 성공적으로 되었을 경우, 명령어를 치고 
```terminal
$ cd .../username.github.io (local 저장소 폴더로 간다)
$ bundle exec jekyll serve

...
...
  Server running... press ctrl-c to stop. # 다음 문장이 뜨면 실행되고 있는 것이다.
```
브라우저에서 **'localhost:4000'**를 입력하면 수정사항이 바로바로 반영된 홈페이지가 뜬다. 서버가 열려있는 동안에는 계속 반영된다.   
**다만, username.github.io/_config.yml을 수정할 경우에는 ctrl-c를 눌러 종료하고 다시 서버를 열어주어야 한다.**

![image7](/assets/images/makeblog/스크린샷, 2020-08-30 17-55-12.png)```테마 적용 결과. 이제 customizaing을 해야 한다.```

이제 다음 글에서는 홈페이지를 내 입맛대로 수정할 것이다.


### 5.References
***
대부분의 과정은 줌코딩님의 게시글을 참고하였다.   
[차근차근 Github 블로그 만들기(1) - Github 블로그 개설 및 테마 설정하기
by 줌코딩](https://zoomkoding.github.io/gitblog/2019/08/15/git-blog-1.html)

-2020.08.30 글 초안 작성
 
