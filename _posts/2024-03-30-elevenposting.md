---
categories: JavaScripts
title: "자바 스크립트 7장 DOM 활용하기 실습보고서 (1)"
date: 2024-04-02 00:23:03
toc: true
---

## 문제1번

## 1.장바구니에 상품 추가하기 실습
<br>

![test1](https://github.com/leejieun9/leejieun9.github.io/blob/master/docs/assets/images/7-1.PNG?raw=true)

<br>

```js
<!DOCTYPE html>
<html lang="ko">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>노드 추가하기</title>
  <style>
    #container {
      border-bottom: 1px dashed #222;
      margin-bottom:20px;
    }
    h1, h2, button, p {
      margin-bottom:20px;
    }
    #cart {
      padding:20px;
    }
  </style>
</head>
<body>
  <div id="container">    
    <h1>상품 설명</h1>
    <h2>HTML+CSS+자바스크립트 웹 표준의 정석</h2>
    <p>한 권으로 끝내는 웹 기본 교과서 </p>
    <p>코딩 완초보도 OK! 기초부터 활용까지 완전정복</p>
    <button id="order">주문하기</button>        
  </div>
  <div id="orderInfo"></div>
  <script>
    const orderButton = document.querySelector("#order")
    const orderInfo = document.querySelector("#orderInfo")
    const title = document.querySelector("#container > h2")

    orderButton.addEventListener("click", () =>{
      let newP = document.createElement("p");
      let textNode = document.createTextNode(title.innerText);

      newP.appendChild(textNode);
      newP.style.fontSize = "0.8em";
      newP.style.color = "blue";
      orderInfo.appendChild(newP);
    }, {once : true});



  </script>
</body>
</html>
```


<br>
<br>
<br>

## 문제 2번

## 2. 시간에 따라 다른 이미지 표시하기 실습
<br>

![test1](https://github.com/leejieun9/leejieun9.github.io/blob/master/docs/assets/images/7-2.PNG?raw=true)

<br>

```js
<!DOCTYPE html>
<html lang="ko">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>노드 추가하기</title>
  <link rel="stylesheet" href="css/main.css">
  <style>
    h1 {
      padding:10px 20px;
      margin-bottom:20px;
      border-radius:8px;
      background-color:#222;
      color:#fff;
      text-transform: uppercase;
    }
  </style>
</head>
<body>
  <div id="container">
    <h1>Enjoy your life</h1>
  </div>
  <script>
    const today = new Date();
    const hrs = today.getHours();
    let newImg = document.createElement("img");
    let srcNode = document.createAttribute("src");
    srcNode.value = (hrs <12)? "images/morning.jpg":"images/afternoon.jpg";
    newImg.setAttributeNode(srcNode);
    //newImg.src = (hrs <12)? "images/monig.jpg":"images/afternoon.jpg";
    const container = document.querySelector("#container");
    container.appendChild(newImg);
  </script>
</body>
</html>
 ```
스크립트 부분
```js
 <script>
    const today = new Date();
    const hrs = today.getHours();
    let newImg = document.createElement("img");
    let srcNode = document.createAttribute("src");
    srcNode.value = (hrs <12)? "images/morning.jpg":"images/afternoon.jpg";
    newImg.setAttributeNode(srcNode);
    //newImg.src = (hrs <12)? "images/monig.jpg":"images/afternoon.jpg";
    const container = document.querySelector("#container");
    container.appendChild(newImg);
  </script>
```



<br>
<br>
<br>


## 문제 3번

## 


```js

```
<br>
<br>
<br>

## 문제 4번

## 4. 나만의 도서 목록 만들기 실습

![test1](https://github.com/leejieun9/leejieun9.github.io/blob/master/docs/assets/images/7-4.PNG?raw=true)

```js
<!DOCTYPE html>
<html lang="ko">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Book List</title>
  <link rel="stylesheet" href="css/bookList.css">
</head>
<body>
  <body>
    <div id="container">
      <h1>Book List</h1>
      <form>
        <ul id="bookInfo">
          <li>
            <label for="title">제 목</label>
            <input type="text" id="title">
          </li>    
          <li>
            <label for="author">저 자</label>
            <input type="text" id="author">
          </li>   
        </ul>
    
        <button type="reset">취소하기</button>
        <button id="save">저장하기</button>
      </form>
      
      <ul id="bookList"></ul>
    </div>
    <script>
      const title = document.querySelector("#title");
      const author = document.querySelector("#author");
      const save = document.querySelector("#save");
      const bookList = document.querySelector("#bookList");
      save.addEventListener("click", (e) => {
        e.preventDefault();
  
     const item = document.createElement("li");
       item.innerHTML = `
        ${title.value} - ${author.value} 
       <span class="delButton">삭제</span>
     `;
    bookList.appendChild(item);
  
    title.value = "";
    author.value = "";
  
    const delButtons = document.querySelectorAll(".delButton");
  
    for (let delButton of delButtons) {
      delButton.addEventListener("click", function () {
        this.parentNode.parentNode.removeChild(this.parentNode);
      });
    }
  });
    </script>
  </body>
</body>
</html>
```

추가한 javascripts
```js
<script>
    const title = document.querySelector("#title");
    const author = document.querySelector("#author");
    const save = document.querySelector("#save");
    const bookList = document.querySelector("#bookList");
    save.addEventListener("click", (e) => {
      e.preventDefault();

   const item = document.createElement("li");
     item.innerHTML = `
      ${title.value} - ${author.value} 
     <span class="delButton">삭제</span>
   `;
  bookList.appendChild(item);

  title.value = "";
  author.value = "";

  const delButtons = document.querySelectorAll(".delButton");

  for (let delButton of delButtons) {
    delButton.addEventListener("click", function () {
      this.parentNode.parentNode.removeChild(this.parentNode);
    });
  }
});
  </script>
```
<br>
<br>
<br>

## 문제 5번
## 5. . 스터디 그룹을 만들기 위해 참가자 명단을 작성하려 한다. 07\quiz-1.html에 필요한 양식이 미리 만들어져 있으므로 이름과 전공을 입력하면 그 값을 받아서 표에 표시하는 소스 코드를 작성하시오.

```js
<!DOCTYPE html>
<html lang="ko">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>연습문제 1</title>  
  <link rel="stylesheet" href="css/quiz-1.css">
</head>
<body>
  <div id="container">
    <h1>참가자 명단</h1>
    <form>
      <ul id="userInput">  
        <li>
          <label for="username">이 름</label>
          <input type="text" id="username">
        </li>    
        <li>
          <label for="major">전 공</label>
          <input type="text" id="major">
        </li>           
      </ul>
      <button>등록하기</button>      
    </form>
    
    <table id="attendant">
      <thead>
        <tr>
          <th>이 름</th>
          <th>전 공</th>
        </tr>
      </thead>
      <tbody></tbody>
    </table>
  </div>
  <script>
const username = document.querySelector("#username");
const major = document.querySelector("#major");
const bttn = document.querySelector("#container button");
const tbody = document.querySelector("#attendant > tbody");
bttn.addEventListener("click",function(e){
  e.preventDefault();

  const trNode = document.createElement("tr");
  const tdNode1 = document.createElement("td");
  const tdNode2 = document.createElement("td");
  tdNode1.innerText=username.value;
  tdNode2.innerText=major.value;
  trNode.appendChild(tdNode1);
  trNode.appendChild(tdNode2);
  tbody.appendChild(trNode);


})

  </script>
</body>
</html>
```
스크립트
```js
 <script>
const username = document.querySelector("#username");
const major = document.querySelector("#major");
const bttn = document.querySelector("#container button");
const tbody = document.querySelector("#attendant > tbody");
bttn.addEventListener("click",function(e){
  e.preventDefault();

  const trNode = document.createElement("tr");
  const tdNode1 = document.createElement("td");
  const tdNode2 = document.createElement("td");
  tdNode1.innerText=username.value;
  tdNode2.innerText=major.value;
  trNode.appendChild(tdNode1);
  trNode.appendChild(tdNode2);
  tbody.appendChild(trNode);


})

  </script>
  ```
