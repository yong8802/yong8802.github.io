---
layout: post
title: React 프로젝트 생성
comments: true
categories: [React]
tags: [React, Typescript]
---

<h5>프로젝트 생성</h5>
1. <span style="color:#ed3249">babel</span> - ECMAScript6를 지원하지 않는 환경에서 사용 할 수 있게 해준다.
2. <span style="color:#ed3249">webpack</span> - 모듈 번들러. Browserify처럼 브라우저에서 import 할 수 있게 해주고 자바스크립트 파일들을 하나로 합쳐준다.
3. <span style="color:#ed3249">webpack-dev-server</span> - 웹서버를 구축할 수 있으며 hot-loader를 통해 코드 반영이 실시간으로 된다.

```$ npm install -g babel webpack webpack-dev-server```

<br/>
<h5>React Typescript 프로젝트 생성</h5>
1. ```npx create-react-app [폴더명] --typescript```
2. ###### ```npm install --save @types/react @types/react-dom``` _// 타입 정의_
3. ###### ```npm install --save-dev typescript``` _//타입스크립트 패키지 설치_
4. ###### ```npx typescript --init``` _//타입스크립트 설정파일 생성_
