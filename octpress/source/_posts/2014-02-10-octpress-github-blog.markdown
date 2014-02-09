---
layout: post
title: "Octpress 를 사용하여 GitHub Pages 에 Blog 만들기"
date: 2014-02-10 02:17:43 +0900
comments: true
categories: tools blog markdown
---

# quick guide

1. github pages 생성 
    * http://pages.github.com/
1. 개인 pc 에 octpress 설치
    * http://octopress.org/docs/setup/
1. octpress 설정
    * http://octopress.org/docs/configuring/
1. test post page 만들기 
    * rake new_post "post title"
    * http://octopress.org/docs/blogging/
1. 생성된 post 파일에 내용 작성 
    * vi source/_posts/2014-02-10-octpress-github-blog.markdown
1. makrdown -> html 으로 변경 
    * rake generate
1. 생성된 blog 와 post page 웹에서 점점 
    * rake preivew
    * localhost:4000 으로 접속
1. 생성된 blog 와 post 를 github pages 에 등록
    * http://octopress.org/docs/deploying/github/ 참고 
    * rake setup_github_pages
    * rake deploy
1. github pages url 로 접속하여 개시된 blog 확인
