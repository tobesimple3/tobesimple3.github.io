---
title:  "Javascript for, map, foreach"    
excerpt: "어떤 Loop를 써야하나." 

categories:
  - javascript
tags:
  - [for]

permalink: /javascript/for-statement/

toc: true
toc_sticky: true
 
date: 2024-08-24
last_modified_at: 2024-08-25
---

## For, Foreach, Map Statement 중에 어떤 Loop를 써야하나.

---

자바스크립트 개발을 하면서, 루프문을 자주 사용하게 된다.
개발에 신경쓰다보면, 자바스크립트 문법보다는 어떻게 쓸까를
고민하게 된다. 일단 개발을 해야하니까. ㅠㅠ.

루프 문에는 for, foreach, map이 있는데.
어떤 것을 사용해야 할지, 정해야 할 때가 있다.
고민이 되는 부분이다.

배열.map(() => { 내용 });

위와 같이 map과 람다를 사용하게 되면 소스가 정말 간결해 진다.

난 foreach 문은 거의 사용하지 않는 거 같다.

주로 for 문을 많이 사용하는거 같다.

일단 단순하게 하나만 고집하게 된다.

**for 문의 장점**

```js
for (let i = 0, x = 0, len = 배열.length; i < len; i++, x++)  {

    // 여기서 len은 배열길이를 상수로 만든다.
    // loop를 돌면서 배열.length를 찾을려면 노동비가 들지 않을까?
    // 상수로 처리하는 것이 더 좋은 거 같다.

    // break, coninue 등을 사용할 수 있다.

}

// 다음은 중첩 for문을 빠져나오는 방법 이다.
// 전에는 for 문 종료를 위해 flag 값을 사용하곤 했다 ㅠㅠ.
let rows = [0, 1, 2];
let cols = [0, 1, 2];
loop1: for (let i = 0; i < rows.length; i++) {
    loop2: for (let x = 0; x < cols.length; x++) {
        console.log(`i ${i} x ${x}`)
        if (cols[x] === 3) {
            break loop1; // loop1 for 문을 break 하란 뜻.
            // continue loop1; // continue도 label 사용가능.
        }
    }
}
```
**for 문의 단점**
```js
for (let i = 0, len = 배열.length; i < len; i++)  {
    for (let x = 0, len2 = 배열.length; x < len; x++)  {

    // 보시다 시피 for 문이 중첩이 되면, 
    // 일단 보기가 과히 좋은거 같지 않다.

    // for와 map을 적정히 사용하는 것이 좋은 거 같다.

    }
}
```
**배열.map() 장점**
```js
배열.map(() => {});
//정말 소스가 단순해 진다. 눈에 보기가 좋다.

배열.map((item, i) => {});
//index를 사용하려면, 위와 같이 쓰면 된다.
```
**배열.map() 단점**
```js
배열.map(() => {});
// 이렇게 쓰게 되면, return 이나 break 같이 
// loop를 빠져나갈 방법이 없다.
// 어차피 배열의 요소가 하나씩 실행되기 때문에..
```
----
