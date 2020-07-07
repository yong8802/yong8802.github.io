---
layout: post
title: Life Cycle API
comments: true
categories: [React]
tags: [React]
---

<h3>컴포넌트 초기 생성</h3>
**constructor**
#####컴포넌트 생성자 함수 - 컴포넌트가 새로 만들어질 때마다 호출 #####
```$xslt
constructor() {
}
```

**componentDidMount**
#####컴포넌트가 화면에 렌더링 될 때 호출 #####
```$xslt
componentDidMount() {
    // 외부 라이브러리 연동
    // 컴포넌트에서 필요한 데이터 요청
    // DOM에 관련된 작업
}
```
<br/>

<h3>컴포넌트 업데이트</h3>
**staticgetDerivedStateFromProps(nextProps, prevState)**
##### - props로 받온 값을 state로 동기화 할 때 사용 #####
##### - 컴포넌트가 마운팅 됬을 때와 업데이트 됬을 경우 호출 #####
##### - nextProps는 부모 컴포넌트로 부터 전달받는 객체 #####
##### - prevState는 렌더링 되기 이전의 state 객체 #####
##### - 메서드를 선언하고 return을 선언하지 않을 경우 warning가 발생 #####
##### - return하는 데이터는 객체여야 한다. #####
```$xslt
staticgetDerivedStateFromProps(nextProps, prevState) {
    // render() 이전의 호출이기 때문에 변경 된 props 데이터를 state에 반영하는 작업을 처리
}
```
