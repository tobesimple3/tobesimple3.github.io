---
title:  "Javascript와 css의 관계는 중요하다."    
excerpt: "Javascript와 css의 관계는 절친인듯." 

categories:
  - javascript
tags:
  - [css]

permalink: /javascript/css/

toc: true
toc_sticky: true
 
date: 2024-08-24
last_modified_at: 2024-08-25
---

## Javascript 개발에서 css의 중요도.

---

Javascript로 컴포넌트 개발을 해본다고 치자.

Html 안에 어떤 엘리먼트가 있다고 하자. 

해당 엘리먼트를 어떻게 가져와야 할까? 

document.getElementById(엘리먼트 아이디) 로 가져와야 할까?

document.querySelector(클랙스 셀렉터) 로 가져와야 할까? 

난 후자의 클랙스 셀렉터로 가져오는 방법을 선호한다.

많은 컴포넌트 들이 클래스 셀렉터로 가져오고 있다.

---

단지, querySelector 는 non-live 라고 한다.

단순하게 설명하자면, <div id='divId" class='class-div' /> 가 있다고 치자.

let element = document.querySelector('.class-div');

let element2 = document.querySelector('.class-div');

element 와 element2는 동일하게 <div id='divId" class='class-div' />를 가르킨다.

만약 element2의 style이나 값이 변했을 경우, element는 반응을 못한다.

이것을 non-live라고 부르는 거 같다. 

특별한 경우 아니면, non-live 생각없이 그냥 사용하면 된다.

---

내가 자바스크립 개발을 하면서 뼈저리게 느꼈던 부분은 다음과 같다.

**javascript를 많이 알수록 그만큼 css도 많이 알아야 한다.**

**css를 많이 알수록 javascript 개발이 편하다.**

예를 들어 스크롤이 됐든 안됐든, 보이는 화면(viewport 라고 한다)에서

element의 위치를 구하는 getBoundingClientRect()는 

viewport 기준으로 위치를 구한다.

element position absolute : 가장 가까운 부모가 relative로 선언된 parent element 기준이다.

element position relative : viewport 기준이다.

여기서 조금더 나아가자면, 컴포넌트를 만들때, 

div relative > div absolute2 > div relative3 > div absolute4, absolute5, absolute6 가 있을때

해당 엘리먼트의 위치를 찾는데 css를 좀 알야 한다.

자바스크립트 개발에서 css는 정말 중요한거 같다.

----

 


