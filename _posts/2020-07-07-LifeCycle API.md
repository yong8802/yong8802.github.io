---
layout: post
title: Life Cycle API
comments: true
categories: [React]
tags: [React]
---

<h3>컴포넌트 초기 생성</h3>

**constructor**
##### 컴포넌트 생성자 함수 - 컴포넌트가 새로 만들어질 때마다 호출 #####
```$xslt
constructor() {
}
```

**componentDidMount**
##### 컴포넌트가 화면에 렌더링 될 때 호출 #####
```$xslt
componentDidMount() {
    // 외부 라이브러리 연동
    // 컴포넌트에서 필요한 데이터 요청
    // DOM에 관련된 작업
}
```
<br/>

<h3>컴포넌트 업데이트</h3>

**static getDerivedStateFromProps(nextProps, prevState)**
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

**shouldComponentUpdate(nextProps, nextState)**
##### 컴포넌트를 최적화 할 때 사용 #####
##### 기본적으로 true를 반환. 불필요한 렌더링을 없애는데 사용 #####
```$xslt
shouldComponentUpdate(nextProps, nextState) {
    // return false 이면 업데이트 안 함
}
```

**getSnapshotBeforeUpdate(prevProps, prevState)**
##### 발생시점
1. render()
2. getSnapshotBeforeUpdate()
3. DOM 변화 발생
4. componentDidUpdate
##### DOM 변화가 일어나기 직전의 DOM 상태를 가져오고, 리턴 값은 componentDidUpdate에서 3번째 파라미터로 받아 올 수 있음

```javascript
getSnapshotBeforeUpdate(prevProps, prevState) {
    // DOM 업데이트가 일어나기 직전의 시점입니다.
    // 새 데이터가 상단에 추가되어도 스크롤바를 유지해보겠습니다.
    // scrollHeight 는 전 후를 비교해서 스크롤 위치를 설정하기 위함이고,
    // scrollTop 은, 이 기능이 크롬에 이미 구현이 되어있는데,
    // 이미 구현이 되어있다면 처리하지 않도록 하기 위함입니다.
    if (prevState.array !== this.state.array) {
      const {
        scrollTop, scrollHeight
      } = this.list;

      // 여기서 반환 하는 값은 componentDidMount 에서 snapshot 값으로 받아올 수 있습니다.
      return {
        scrollTop, scrollHeight
      };
    }
  }

  componentDidUpdate(prevProps, prevState, snapshot) {
    if (snapshot) {
      const { scrollTop } = this.list;
      if (scrollTop !== snapshot.scrollTop) return; // 기능이 이미 구현되어있다면 처리하지 않습니다.
      const diff = this.list.scrollHeight - snapshot.scrollHeight;
      this.list.scrollTop += diff;
    }
  }
```

**componentDidUpdate(prevProps, prevState, snapshot)**
```javascript
componentDidUpdate(prevProps, prevState, snapshot) {

}
```
