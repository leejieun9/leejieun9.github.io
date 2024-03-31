---
categories: JavaScripts
title: " 자바스크립트 5장 DOM 기초 연습문제"
date: 2024-03-26 00:23:03
toc: true
---

## 문제1번

## 1. 1. desc라는 id 선택자를 사용한 요소에 접근하는 코드를 작성해 보세요.
 <br>

```js
document.querySelector("#desc")
```
<br>
<br>
<br>
<br>

## 문제 2번

## 2. 05\index.html에서 '주소 : somewhere'에 접근하는 코드를 작성해 보세요.

```js
document.querySelectorAll(".user")[1]
  ```
<br>
<br>


## 문제 3번

## 3.3. 05\js-content-2.js를 수정해서 연락처를 클릭하면 '1234-5678'이 '1111-2222'로 바뀌게 하시오.

 <br>
```js

<!DOCTYPE html>
<html lang="ko">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>웹 요소에 접근하기</title>
  <link rel="stylesheet" href="css/main.css">
  <link rel="stylesheet" href="css/style.css">
</head>
<body>
  <h1 id="title">My Profile</h1>
  <div id="profile">
    <img src="images/pf.png" alt="도레미">
    <div id="desc">
      <p class="user">이름 : 도레미</p>
      <p class="user">주소 : somewhere</p>
      <p class="user">연락처 : 1234-5678</p>
    </div>
  </div>

  <script src="js/js-content-2.js"></script>
</body>
</html>
```

```js

const title = document.querySelector("#title");
const userName = document.querySelector("#desc p");
const pfImage = document.querySelector("#profile img");
const contact = document.querySelectorAll(".user")[2]

title.onclick = () => title.innerText = "프로필";    
userName.onclick = () => userName.innerHTML = `이름 : <b>민들레</b>`;
pfImage.onclick = () => pfImage.src = "images/pf2.png";
contact.onclick = () => contact.innerText = "연락처 : 1111-2222"

```
<br>
<br>
<br>
<br>
<br>
  
## 문제4번

## 4. 05\js-css.js를 수정해 '이름 도레미' 부분을 클릭하면 글자색이 red로 바뀌는 코드를 작성해 보세요.

```js

const title = document.querySelector("#title");
const name = document.querySelector(".user")

title.onclick = () => {
  title.style.backgroundColor = "black";
  title.style.color = "white";
};

name.onclick = () => name.style.color = "red";
```
 <br>

## 문제5번

## 5.  style.css 파일에는 .blue-italic 스타일도 정의되어 있으므로 05\js\classlist-3.js 파일을 수정해 '이름:도레미' 부분을 클릭할 때마다 이 스타일을 토글시키는 소스를 작성해 보세요.
  
  ```js
const title = document.querySelector("#title");

title.onclick = () => {
  title.classList.toggle("clicked");
}

const name = document.querySelector(".user");
name.onclick = () => {
  name.classList.toggle("blue-italic");
}
```

<br>
<br>

## 문제6번

## 6. 05\order.html 문서에서 '상품' 항목에 내용을 입력한 후 자바스크립트를 사용해 입력한 내용을 가져오는 코드를 작성해 보세요.

```js
orter.html 에서 서버를 열어 상품에 (ex.스마트폰)을 넣고 콘솔창에서 상품을 불러오면
    >>  document.querySelector("#product").value
    라고치면 '스마트폰' 이 나온다.

```

## 문제7번
___

## ​7.7. 05\login.html 문서에서 '아이디' 필드에 있는 값을 가져오는 소스를 작성해 보세요.
```js

login.html 에서 서버를 열어 로그인에 (ex.lee)를 적어놓고 아래의 코드를 돌리면
document.forms[0].elements[0].value
>>아이디 필드에 있는 lee 라는 값이 나온다.

```

## 문제8번

## 8번. 8. 05\quiz-1.html 문서에는 [상세 설명 보기 / 닫기] 버튼이 있는데, 이 버튼을 클릭할 때마다 상세 설명이 나타나거나 사라지도록 코드를 작성해 보시오.

힌트:

상세 설명이 있는 영역을 가져와서 변수로 저장한다.

버튼을 가져와서 변수로 저장한다.

문서에는 .hidden {display: none; } 스타일이 만들어져 있다.

버튼을 클릭할 때마다 클래스 리스트의 toggle() 함수를 사용해 .hidden 스타일이 토글되도록 한다.

[코드]

```js
  <script>
    const detail = document.querySelector ("#detail")
    const button = document.querySelector("#view")
    button.onclick = () => {
      detail.classList.toggle("hidden");
    }
  </script>
```
​
<br>
<br>

## 문제9번

## 4장에서 작성한 '두 수의 최대공약수 구하기' 함수를 그대로 사용화면서 화면에 2개의 값을 입력한 후 [계산하기] 버튼을 클릭했을 때 함수를 실행하고,
*함수의 실행 결과는 '결과' 항목에 표시해 보시오(05\quiz-2.html 사용)*


```js
const n = document.querySelector("#number1");
const m = document.querySelector("#number2");
const button = document.querySelector("button");
let result = document.querySelector("#result");

button.onclick = function() {
  result.innerText = getGCD(n.value, m.value);
}

function getGCD(n, m) {
  let max = n > m ? n : m;
  let GCD = 0;
  for (let i = 1; i <= max; i++) {
    if (n % i === 0 && m % i === 0) {
      GCD = i;   
    }
  }
  return GCD;
}

  ```
<br>
<br>

~~다행이다 수업들어서,,,,~~
