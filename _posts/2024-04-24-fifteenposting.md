---
categories: JavaScripts
title: " 자바스크립트 10장 문자열과 배열 활용하기 보고서"
date: 2024-03-24 00:23:03
toc : true
---

***
요즘 아무것도 하기싫다..



***
<br>

## 문제1번

## 1. charAt() 메서드를 사용해서 greeting 변수의 세 번째 문자에 접근하는 소스를 작성해보세요. <br>

```js
greeting.charAt(2);

```


## 문제 2번

## 2. 교재 p.340의 소스에서 if 문에 대괄호 대신 charAt() 메서드를 사용하시오. <br>

```js
if(str[i] == ch ) --> if(str.charAt(i) == ch)
```
<br>
<br>
<br>

## 문제 3번

## 3. str1 문자열에서 문자열 "everyone"이 어느 위치에서 나타나는지 찾아보세요. <br>

```js
str1.indexOf("everyone");
```
<br>
<br>
  
## 문제4번

## 4. "good moring".startWith("o", 2)의 결과 값은? <br>
```js
답 : TRUE
```

<br>
<br>

## 문제5번

## 5. "Hello, everyone.".endwidth("l", 4)의 결과 값는?
```js
답 : TRUE
```
<br>
<br>

## 문제6번

---

## 6. str2 문자열에 one이 포함되어 있는 지 확인하는 소스를 작성해 보세요. <br>
<br>

```js
str2.includes("one");

```
<br>

## 문제7번
___

## 7. "Hello, everyone." 문자열에서 everyone.만 추출해 보세요.

```js
"Hello,everyone.".substring(7);
```

## 문제 8번
---
## 다음 소스코드를 실행했을 때 결과값은?

```js
let arr = [0, 1, 2, 3, 4, 5];
arr.slice(-1);
```

## [결과값]
```js
답 : [5]
```

## 문제 9번


## 9. 웹 주소 웹 주소 https://cafe.naver.com/doitstudyroom 을 프로토콜과 도메인, 페이지로 구분하시오. 이때 구분자로 /를 사용하시오 <br>

```js
"https://cafe.naver.com/doitstudyroom".split("/");
---> 결과 :[https:","","cafe.naver.com","doistudyroom"]
```

## 문제 10번

## 10. 보안을 위해 이메일 주소의 일부 감추기
```js
<!DOCTYPE html>
<html lang="ko">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>메일 주소 일부 가리기</title>
  <link rel="stylesheet" href="css/email.css">
</head>
<body>  
  <div id="userInput">
    <label>
      <input type="email" id="userEmail" placeholder="이메일 주소를 입력하세요." autofocus>
    </label>
    <button>실행</button>
  </div>  
  <div id="result"></div>
  <script>
    const bttn = document.querySelector("button").addEventListener("click",function(){
    let email = document.querySelector("#userEmail").value;
    let arr = email.split("@");
    let id = arr[0];
    let domain = arr[1];
    let hiddenId = id.substring(0,3);
    let resultText = `${hiddenId}...@${domain}`;
    document.querySelector("#result").innerHTML = resultText;
    });
    
  </script>

</body>
</html>
```
[스크립트 부분]
```js
  <script>
    const bttn = document.querySelector("button").addEventListener("click",function(){
    let email = document.querySelector("#userEmail").value;
    let arr = email.split("@");
    let id = arr[0];
    let domain = arr[1];
    let hiddenId = id.substring(0,3);
    let resultText = `${hiddenId}...@${domain}`;
    document.querySelector("#result").innerHTML = resultText;
    });
    
  </script>
```

## 12번

## 12. 전개 연산자를 사용해 vegitable 배열과 cheese 배열을 합친 후에 맨 마지막에 빵까지 합쳐서 cheeseBurger2 배열을 만들어 보세요.
```js
let cheeseBurger2 = [...vegitable,...cheese,"빵"]
```
<br>
<br>

## 13번

## 13. slice() 함수를 사용해 colors 배열에서 blue와 white를 추출하시오.
```js
let colors = ["red","green","blue","white","black"];
let newColors = colors.slice(2,4);
```
## 14번

---
## 14. 10\quiz-1.html 문서에는 [2, 4, 6, 8, 10]이라는 배열이 있는데, 이 배열을 화면에 표시하고 배열의 요소를 모두 더한 후 마지막에 결괏값을 추가하는 프로그램을 작성하시오.
```js
<!DOCTYPE html>
<html lang="ko">
<head>
   <meta charset="UTF-8">
   <meta name="viewport" content="width=device-width, initial-scale=1.0">
   <meta http-equiv="X-UA-Compatible" content="ie=edge">
   <title>연습 문제 1</title>
   <style>
    #container {
      width:500px;
      margin:20px auto;
    }
    h1 {
      font-size:1.5em;
    }
      table, td {
      border:1px solid #ccc; 
      border-collapse: collapse; 
      margin-bottom:20px;
    }
      td { 
      padding:5px 10px;
      font-size:1.5em;
    }
    #result td:last-child {
      background-color:#222;
      color:#fff;
    }
   </style>
</head>
<body>
  <div id="container">
    <h1>주어진 배열 : [2, 4, 6, 8, 10]</h1>
    <hr>
    <h1>원래 배열</h1>
    <div id="origin"></div>
  
    <h1>모든 값을 더한 배열</h1>
    <div id="result"></div>
  </div>
<script>
  const origin = document.querySelector("#origin");
  const result = document.querySelector("#result");
  function displayArray(area,array){
    let text = "<table> <tr>"
      for (let i = 0; i<array.length; i++){
        text += `<td>${array[i]}</td>`;

      }
      text += "</tr></table>";
      area.innerHTML = text;
  }
  const arr = [2,4,6,8,10];
  displayArray(origin , arr);

//합을 구한다.
let sum = 0;
for ( let i =0; i<arr.length; i++){
  sum +=  arr[i]
}
//합을  arr의 마지막에 넣는다.
arr.push(sum)
displayArray(result,arr);
//displatArray를 호출한다.
</script>
</body>
</html>
```
## [스크립트 부분]

```js
<script>
  const origin = document.querySelector("#origin");
  const result = document.querySelector("#result");
  function displayArray(area,array){
    let text = "<table> <tr>"
      for (let i = 0; i<array.length; i++){
        text += `<td>${array[i]}</td>`;

      }
      text += "</tr></table>";
      area.innerHTML = text;
  }
  const arr = [2,4,6,8,10];
  displayArray(origin , arr);

//합을 구한다.
let sum = 0;
for ( let i =0; i<arr.length; i++){
  sum +=  arr[i]
}
//합을  arr의 마지막에 넣는다.
arr.push(sum)
displayArray(result,arr);
//displatArray를 호출한다.
</script>

```

![test](https://github.com/leejieun9/leejieun9.github.io/blob/master/docs/assets/images/10-1.PNG?raw=true)
## 15번

---
## 15. 10\js\quiz-2.js 파일에 작성한 다음의 소스를 참고해서 tail() 함수를 작성해 보세요. tail() 함수는 배열을 받아서 배열의 길이가 1보다 크면 첫 번째 요소를 뺀 나머지 요소를, 배열의 길이가 1이면 배열 전체를 반환합니다.

```js
```

