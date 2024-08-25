---
title:  "자바스크립에서 실행 속도 개선."    
excerpt: "자바스크립에서 실행 속도 개선." 

categories:
  - javascript
tags:
  - [speed]

permalink: /javascript/how-to-speed/

toc: true
toc_sticky: true
 
date: 2024-08-24
last_modified_at: 2024-08-25
---

## 자바스크립 속도 개선

---

해당 게시글은 앞으로 계속 업데이트 하겠지만, 

어떻게 하면 자바스크립트를 좀 더 빠르게 실행 시킬 수 있는지 

내 경험상 얘기를 하고 싶다.

요즘은 AI 들이 알아서 해준다고 하는데, 그건 잘 모르겠음.

우선적으로 HTML 안에는 여러가지 내용들이 있고, 

구글, 엣지, 사파리 브라우저들은 해당 내용들을 읽어서, 

브라우저 안에 컴포넌트들로 정보를 저장하게 된다.

결국 자바스크립트는 브라우저 컴포넌트 정보들을 이용하게 된다.

----

## Element style이나 값 변경하기.

Html Element의 style 혹은 값을 읽는 것과 쓰는 것은 차이가 크다. 

```js
let element = document.querySelector(엘리먼트의 클래스);
// 속도는 빠르다.

let value = element.textContent;
// 속도는 빠르다.

element.textContent = '값'
// 속도는 느리다. 암튼 element 들에 대해 어떤 값을 넣고 바꾸면 느려진다.

if (element.textContent != '값') element.textContent = '값';
// 읽는 건 빠르고 쓰는 건 느리므로, 불필요한 입력은 피하는 것이 낫다.
```

---

## 불필요한 코딩을 피하기.

좀 원론적인 말이긴 하지만, 불필요한 코딩이 어디서 발생되는지를 알아야 한다.

문법적인 부분은 결국 나중에 구력이 쌓이면 해결될 문제다.

예를 들어, 어떤 object[][] 배열 중에 요소를 3개 삭제 혹은 추가 하고 싶다. 

우선적으로 1개를 추가, 삭제 하는 함수를 만든다.

그리고 여러개를 추가, 삭제하는 로직은 1개를 추가 삭제 하는 함수를 이용하면 된다.

만약에 여러개를 한번에 추가하는 함수를 만들면 소스량도 많아지고, 가독성도 떨어진다.

속도 향상에도 도움이 된다.

---

## for 문 사용시

만약 배열을 for문으로 돌리게 된다면, 다음과 같이 배열의 길이를 

상수로 잡는 것도 좋은 방법이라고 생각한다.

```javascript
for (let i = 0, len = 배열.length; i < len; i++) {}
for (let i = 0, len = document.selectorAll('셀렉터').length; i < len; i++) {}
```
---
 


