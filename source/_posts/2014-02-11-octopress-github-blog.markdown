---
layout: post
title: "Octopress 를 사용하여 GitHub Pages 에 Blog 만들기"
date: 2014-02-11 00:47:13 +0900
comments: true
categories: markdown blog tools
---

# quick install guide

1. github pages 생성
    * http://pages.github.com/
* 개인 pc 에 octopress 설치
    * http://octopress.org/docs/setup/
* octopress 설정
    * http://octopress.org/docs/configuring/
    * test post page 만들기
    * rake new_post["post title"]
    * http://octopress.org/docs/blogging/
* 생성된 post 파일에 내용 작성
    * vi source/_posts/2014-02-10-octopress-github-blog.markdown
* markdown –> html 으로 변환
    * rake generate
    * markdown 문법 아래 참고
        * http://ko.wikipedia.org/wiki/%EB%A7%88%ED%81%AC%EB%8B%A4%EC%9A%B4
        * http://daringfireball.net/projects/markdown/syntax
        * https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet
* 생성된 blog 와 post page 웹에서 점점
    * rake preivew
    * localhost:4000 으로 접속
* 생성된 blog 와 post 를 github pages 에 등록
    * rake setup_github_pages
    * rake deploy
    * http://octopress.org/docs/deploying/github/ 참고
* github pages url 로 접속하여 개시된 blog 확인
    * http://kaurikim.github.io
