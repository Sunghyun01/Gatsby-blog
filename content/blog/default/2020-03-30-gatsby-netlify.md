---
title: Gatsby + Netlify
category: default
draft: false
date: 2020-03-30T03:27:11.407Z
description: 간단소개
---
## Wappalyzer

![Wappalyzer](/img/캡처.png "Wappalyzer")

## 구조

![dir](/img/dir.png "dir")

>root

>├──gatsby-browser.js // font, polyfill, onClientRender ...

>├──gatsby-config.js // Gatsby config

>├──gatsby-meta-config.js // Template meta config

>└──gatsby-node.js // Gatsby Node config

>asset : 기본 이미지파일

>content

>├──_about : 자기소

>├──assets : 블로그 아이콘 + 사용자 아이콘

>└──blog : 블로그 콘텐츠

>    >├──default : default 카테고리

>    >├──test : test 카테고리

>    >└──university : university 카테고리 

>src

>├──components // 컴포넌트 + 스타일

>├──layout // home, post layout

>├──pages // 라우트 /(home), /about

>├──styles

>    >├──code.scss

>    >├──dark-theme.scss

>    >├──light-theme.scss

>    >└──variables.scss

>└──templates

>    >├──blog-post.js

>    >└──home.js

>static

>└──config.yml

## Gatsby

React와 Graphql을 사용하는 정적페이지 생성기

## Graphql

___graphql

## Netlify

Netlift는 정적 페이지를 무료로 빌드 및 배포할 수 있게 도와주는 사이트.

 특징은 HTTPS 를 제공하며, Github 의 특정 Repo 의 특정 브랜치가 Push 될때 마다 자동 빌드

## 참고링크

<a href="https://www.gatsbyjs.org/showcase/?filters[0]=Featured">템플릿 모음</a>

<a href="https://github.com/JaeYeopHan/gatsby-starter-bee">starter-bee</a>

<a href="https://gist.github.com/ihoneymon/652be052a0727ad59601">MarkDown</a>

<a href="https://www.gatsbyjs.org/">Gatsby</a>

<a href="https://app.netlify.com/">Netlify</a>

<a href="https://www.netlifycms.org/">Netlify CMS</a>

<a href="https://graphql.org/">Graphql</a>

## config.yml

```yaml
backend:
   name: github
   repo:  Sunghyun01/Gatsby-blog
   branch: master
media_folder: static/img
public_folder: /img
collections:
   - name: 'test'
     label: 'test'
     folder: 'content/blog/test'
     create: true
     slug: '{{year}}-{{month}}-{{day}}-{{slug}}'
     editor:
       preview: true
     fields:
       - { label: 'Title', name: 'title', widget: 'string' }
       - { label: 'category', name: 'category', widget: 'hidden', default: 'test'}
       - { label: 'Draft', name: 'draft', widget: 'hidden', default: false}
       - { label: 'Publish Date', name: 'date', widget: 'datetime' }
       - { label: 'Description', name: 'description', widget: 'string' }
       - { label: 'Body', name: 'body', widget: 'markdown' }
```