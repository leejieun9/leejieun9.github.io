---
categories: JavaScripts
title: " 자바스크립트 6장 이벤트와 이벤트처리 연습문제"
date: 2024-04-01 22:09:03
toc: true
---

## 문제1번

## 1. 06\js\event-2.js 나 event-3.js 를 참고해서 [Click] 버튼을 클릭했을 때 문서의 배경색은 #222로, 글자색은 #fff로 변경하는 소스를 작성해 보세요.
*이때 웹 문서에 약간의 텍스트가 있어야 글자색이 바뀌는 것을 확인할 수 있는데, 문서의 텍스트는 직접 입력하세요.*

*작성할 파일 - 06\q0.html, 06\js\q01.js 
//q.01.js 파일이 없으므로 html안에서 같이하는 걸로 대체*

```js
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Document</title>
</head>
  <body>
    <h1>문제 1번</h1>
    <button>클릭</button>
    <script>
      document.querySelector("button").onclick = () =>{
        document.body.style.backgroundColor = "#222";
        document.body.style.color = "#fff";
      }
    </script>
  </body>
</html>
```

<br>
<br>
<br>
<br>

## 문제 2번

## 2. addEventListener() 함수를 사용해서 버튼을 클릭했을 때 문서의 배경색과 글자색을 토글하는 소스를 작성해 보세요.
<br>

```js
//작성할 파일 - 06\q0.html, 06\js\q01.js  q.02.js 파일이 없으므로 html안에서 같이하는 걸로 대체

<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Document</title>
  <style>
    .convert {
      background-color:#000000;
      color:#fdfdfd;
    }
  </style>
</head>
<body>
  <p>버튼을 클릭하면 배경색과 글자색이 바뀝니다.</p>
  <button>click</button>
  <script>
    const bttn = document.querySelector("Button")
    bttn.addEventListener("click",() => {
      document.body.classList.toggle("convert");
    })
  </script>
</body>
</html>
```
<br>
<br>
<br>
<br>

## 문제 3번

## 3. 모달박스 실습문제

하...이게 진짜 별거 아니였는데 오타때문에 한시간 잡아먹은 썰 푼다...하하하하하하 modal 인데 model....하...이녀석 왜 안보이냐고...

![test1](https://github.com/leejieun9/leejieun9.github.io/blob/master/docs/assets/images/6-4.PNG?raw=true)

![test1](https://github.com/leejieun9/leejieun9.github.io/blob/master/docs/assets/images/6-5.PNG?raw=true)

## 문제 4번

## 4. 06\js\event-6.js 파일을 참고해 사각형 영역에서 마우스를 움직일 때, 즉 mousemove 이벤트가 발생할 때 이벤트의 발생 위치를 콘솔 창에 보여주는 소스를 작성해 보세요
<br>
<br>
```js
 <br>
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Document</title>
</head>
<style>
  p {
    font-size:1.2rem;
    margin-bottom:20px;
  }
  #box{
    width:200px;
    height:200px;
    border:1px solid #222;
    border-radius:5%;
  }

</style>
<body>
  <div id = "box"></div>
  <script>
    const box = document.querySelector("#box");
    box.addEventListener("mousemove",(e)=>{
      console.log ('(${e.pageX} , ${e.pageY})');
    })
  </script>
</body>
</html>
```

<br>
<br>
<br>
<br>

## 문제5번

## 5. 자바스크립트로 캐러셀 만들기 실습

![test1](https://github.com/leejieun9/leejieun9.github.io/blob/master/docs/assets/images/6-6.PNG?raw=true)
<br>
<br>
![test1](https://github.com/leejieun9/leejieun9.github.io/blob/master/docs/assets/images/6-7.PNG?raw=true)

<br>
<br>

## 문제6번

## 6. 06\quiz-1.html 문서에는 하나의 이미지가 삽입되어 있습니다. 이 이미지의 위에 마우스 포인터를 올려 놓았을 때 06\images\pic-6.jpg로 바뀌었다가 마우스 포인터를 다른 곳으로 이동하면 06\images\pic-1.jpg로 바뀌는 소스를 작성해 보세요.

```js
<!DOCTYPE html>
<html lang="ko">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>연습문제 1</title>  
  <style>
    #container {
      width: 600px;
      margin: 20px auto;
    }
    h1 {
      font-size:1.5rem;
      text-align:center;
      margin-bottom:20px;
    }
  </style>
</head>
<body>
  <div id="container">
    <h1>마우스 오버하면 이미지 바꾸기</h1>
    <img src="images/pic-1.jpg" alt="">
    <script>
  const img = document.querySelector("img");
    img.addEventListener("mouseover", ()=>{
    img.src="images/pic-6.jpg";
  });
    img.addEventListener("mouseout", ()=>{
    img.src="images/pic-1.jpg";
});
    </script>
  </div>
</body>
</html>

```
<br>
<br>
## 문제7번
___

## ​7. 이벤트를 활용해 따라 표시했다가 감추는 메뉴를 만들어 보겠습니다. 여기에서는 아이콘을 클릭하면 메뉴가 표시되고, 다시 클릭하면 메뉴가 숨겨지는 예제를 만들 것입니다. 06\css\solution-2.css 파일에는 버튼과 메뉴에서 사용할 .active 스타일이 미리 만들어져 있습니다. 버튼을 클릭할 때마다 변수와 메뉴에 .active 스타일을 토글하는 소스를 만들어 보세요.

### 힌트

*웹 문서에 연결된 외부 스타일 시트 파일에 button.active와 nav.active 스타일이 미리 만들어져 있습니다.*

*버튼과 메뉴를 가져와서 각각 변수로 저장합니다.*

*버튼에 click 이벤트가 발생했을 때 실행할 함수를 연결하는데, 이 함수에서는 버튼과 메뉴에 active 클래스 스타일을 토글합니다.*
<br>
<br>
```js
//사용할 파일 06\quiz-2.html , 06\js\quiz-2.js (신규 작성)

 <link rel="stylesheet" href="css/solution-2.css">
</head>
<body>
  <button id="bttn">&#9776;</button>

  <nav id="nav">
    <ul>
      <li><a href="#">Javascript</a></li>
      <li><a href="#">Typescript</a></li>
      <li><a href="#">Node.js</a></li>
    </ul>
  </nav>
  <script>
    const bttn = document.querySelector("#bttn");
    const nav = document.querySelector("#nav");
    bttn.addEventListener("click",() => {
      bttn.classList.toggle("active");
      nav.classList.toggle("active");
    });
  </script>

```
<br>
<br>
