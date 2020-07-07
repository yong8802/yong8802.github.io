---
layout: post
title: React 프로젝트 생성
comments: true
categories: [React]
tags: [React, Typescript]
---

<h3>프로젝트 생성 준비</h3>
1. <span style="color:#ed3249">Node.js</span> - webpack과 babel같은 도구들이 javascript 런타임인 node.js 기반으로 만들어져 있기 때문에 해당 도구들을 사용하기 위해 설치
2. <span style="color:#ed3249">Yarn</span> - npm보다 속도와 캐싱이 빠르다.

[Node LTS 버전 다운로드](https://nodejs.org/ko/download/)

[Yarn 설치](https://yarnpkg.com/en/docs/install)

<br/>

<h4>React 프로젝트 생성</h4>
##### npm #####
```$xslt
$ npm install -g create-react-app
```
##### yarn #####
```$xslt
$ yarn add -g create-react-app
```
##### linux나 maxOS에서 nvm을 통하여 node.js를 설치 했을 경우 yarn Path 입력
```$xslt
# macOS:
echo 'export PATH="$(yarn global bin):$PATH"' >> ~/.bash_profile
# Linux:
echo 'export PATH="$(yarn global bin):$PATH"' >> ~/.bashrc
```
##### 프로젝트 생성 #####
``` create-react-app [프로젝트명]```
```$xslt
cd [프로젝트명]
yarn start
```


<br/>
<h3>React Typescript 프로젝트 생성</h3>

```$xslt
npx create-react-app [폴더명] --typescript
npm install --save @types/react @types/react-dom // 타입 정의
npm install --save-dev typescript //타입스크립트 패키지 설치
npx typescript --init //타입스크립트 설정파일 생성
```



