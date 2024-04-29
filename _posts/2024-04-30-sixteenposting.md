---
categories: JavaScripts
title: " 자바스크립트 11장 배열과 객체 더 깊게 살펴보기 보고서"
date: 2024-03-30 00:23:03
toc : true
---

***
요즘 업데이트가 뜸한이유가 있다. <br>
사실 안올리는 것이 아니라 못올리는 거다.<br>
이유는 9장 10장 연습문제랑 과제를 아직 완성을 못했기 때문에 미리 해도 못올리는 이유다.ㅋㅋㅋ..<br>
히히..진짜 이번주에는 꼭 끝내야징<br>
***
<br>

## 문제1번

### 1. ["봄", "여름", "가을", "겨울"] 배열에서 세 번째, 네 번째 요소를 각각 fall과 winter라는 변수에 할당해 보세요.

[코드]
 <br>

```js
let [, ,fall,winter] = ["봄" , "여름", "가을" , "겨울"]
```


## 문제 2번

### 2. [실습] 개설 요청 과목 정리하기

[코드]
 <br>

```js
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>개설 강좌 신청</title>
  <style>
    #container{
      width:400px;
      margin:20px auto;
    }
    hr {
      width:100%;
      border:1px dotted #222;
    }
    ul {
      list-style: none;
    }
    li {
      font-size:1rem;
      line-height: 2;
    }
  </style>
</head>
<body>
  <div id="container">
    <h1>신청 과목</h1>    
    <ul>
      <li>member1 : HTML, CSS</li>
      <li>member2 : CSS, 자바스크립트, 리액트</li>
      <li>member3 : 자바스크립트, 타입스크립트</li>
    </ul>
    <hr>
    <h2>최종 신청 과목</h2>
    <div id="result"></div>
  </div>
<script>
  const member1 = ["HTML", "CSS"];
  const member2 = ["CSS", "자바스크립트", "리액트"];
  const member3 = ["자바스크립트", "타입스크립트"];
  const subjects = [...member1, ...member2, ...member3];
  console.log(subjects);

const resultList = new Set();
  subjects.forEach(subject => {
    resultList.add(subject);
    result.innerHTML = `<ul>${[...resultList].map( subject => `<li>${subject}</li>`).join("")}</ul>`;
});
</script>
</body>
</html>
```
<br>

### [스크립트 부분]

```js
<script>
  const member1 = ["HTML", "CSS"];
  const member2 = ["CSS", "자바스크립트", "리액트"];
  const member3 = ["자바스크립트", "타입스크립트"];
  const subjects = [...member1, ...member2, ...member3];
  console.log(subjects);

const resultList = new Set();
  subjects.forEach(subject => {
    resultList.add(subject);
    result.innerHTML = `<ul>${[...resultList].map( subject => `<li>${subject}</li>`).join("")}</ul>`;
});
</script>
```
<br>
<br>

## 문제 3번

### 3. [마무리 문제2] 자바스크립트를 사용해서 자동으로 복권 번호를 생성해 주는 프로그램을 작성하려 합니다. 번호는 증복되면 안되므로 셋을 이용할 것이고, 숫자는 1부터 45까지의 범위 안에 있어야 하며, 6개의 무작위 수를 추출할 것입니다. 버튼을 클릭했을 때 모든 조건을 반영해서 6개의 숫자를 추출하는 소스를 작성해 보세요.

[코드]
 <br>

```js
  <script>
   let numbers = new Set();
    // Set를 배열로 변환
    let lottoNumbers = Array.from(numbers);
    let button = document.querySelector("button");

      // 로또번호 출력
      let resultDiv = document.getElementById("result");
    resultDiv.innerHTML = lottoNumbers.join(",");

    button.addEventListener("click", function() {
      // 로또번호 생성 및 출력
      let numbers = new Set();
      for (let i = 0; i < 6; i++) {
        let randomNumber = Math.floor(Math.random() * 45) + 1;
        numbers.add(randomNumber);
      }
      let lottoNumbers = Array.from(numbers);
      let resultDiv = document.getElementById("result");
      resultDiv.innerHTML = lottoNumbers.join(",");
    });

  </script>
```
<br>
<br>
  
