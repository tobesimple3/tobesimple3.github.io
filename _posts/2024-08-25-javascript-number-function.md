---
title:  "Number 함수"    
excerpt: "Number 함수를 알아보자." 

categories:
  - javascript
tags:
  - [Number]

permalink: /javascript/number-function/

toc: true
toc_sticky: true
 
date: 2024-08-24
last_modified_at: 2024-08-25
---

## Number 함수에 대해 알아보자.

---

개발중에 숫자 관련해서, 구현해야 할 내용이 많았다.

그런데, 가끔 기본을 잊고 프로그램을 할 때가 있다.


데이타베이스도 마찬가지 인거 같다.

sum(null), 1 + null  등을 입력해봐서 실제로 어떻 값이

나오는지 알아야 한다.

**Number 함수를 사용해서 테스트 했다.**

```js
let a; // 선언만 한 상태. a == undefined 

console.log(`Number(a) ${Number(a)}`); // NaN (Not a Number)

console.log(`Number(null) ${Number(null)}`); // 0

console.log(`Number(' ') ${Number(' ') }`); // 0

console.log(`Number('') ${Number('') }`); // 0

console.log(`Number(true) ${Number(true)}`); // 1

console.log(`Number(false) ${Number(false)}`); // 0

// 특히, null 값과 undefined 값에 대해 잊고 살았던거 같다.
```
----
