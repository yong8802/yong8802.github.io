---
layout: post
title: React 프로젝트 생성
comments: true
categories: [React]
tags: [React, Typescript]
---

### **프로젝트 생성 준비**
1. <span style="color:#ed3249">Node.js</span> - webpack과 babel같은 도구들이 javascript 런타임인 node.js 기반으로 만들어져 있기 때문에 해당 도구들을 사용하기 위해 설치
2. <span style="color:#ed3249">Yarn</span> - npm보다 속도와 캐싱이 빠르다.

[Node LTS 버전 다운로드](https://nodejs.org/ko/download/)

[Yarn 설치](https://yarnpkg.com/en/docs/install)

<br/>

<h4> React 프로젝트 생성 </h4>

##### npm
```shell script
$ npm install -g create-react-app
```

##### yarn
```shell script
$ yarn add -g create-react-app
```
##### linux나 maxOS에서 nvm을 통하여 node.js를 설치 했을 경우 yarn Path 입력

```shell script
# macOS:
echo 'export PATH="$(yarn global bin):$PATH"' >> ~/.bash_profile
# Linux:
echo 'export PATH="$(yarn global bin):$PATH"' >> ~/.bashrc
```

##### 프로젝트 생성 #####
```shell script
create-react-app [프로젝트명]
cd [프로젝트명]
yarn start
```


<br/>

<h3>React Typescript 프로젝트 생성</h3>

```shell script
npx create-react-app [폴더명] --typescript
npm install --save @types/react @types/react-dom // 타입 정의
npm install --save-dev typescript //타입스크립트 패키지 설치
npx typescript --init //타입스크립트 설정파일 생성
```

tsconfig.js 파일 수정
```js
{
  "compilerOptions": {
    "sourceMap": true,
    "target": "es5", // 사용할 ECMAScript 버전 설정
    "jsx": "react", // jsx 지원
    "module": "esnext", // 모듈 설정
    "moduleResolution": "node", // 모듈 해석 방식 설정
    "emitDecoratorMetadata": true, // @TODO 테스트 필요
    "experimentalDecorators": true, // ES Decorator에 대한 실험적 기능 사용 여부
    "declaration": false, // .d.ts파일의 생성 여부
    "noImplicitAny": false, // any 타입 금지
    "noImplicitReturns": false, // 함수의 모든 경로가 값을 반환하지 않으면 에러 발생
    "noUnusedLocals": true, // 사용 안 된 지역 변수에 대한 오류 보고 여부
    "removeComments": true, // 주석 삭제
    "strictNullChecks": false, // null과 undefined 타입 구분 여부
    "resolveJsonModule": true,
    "esModuleInterop": true, // https://
    "outDir": "build", // 출력할 디렉토리
    "lib": ["es6", "es7", "dom"], // 컴파일에 포함 될 라이브러리 파일 목록
    "baseUrl": "src", // Non-relativ 모듈 혹은 paths 옵션의 기준 디렉토리
  }
}
```


