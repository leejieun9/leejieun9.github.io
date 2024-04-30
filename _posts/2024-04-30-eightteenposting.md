---
categories: JavaScripts
title: " 12장 HTTP 통신과 JSON 실습보고서"
date: 2024-04-30 08:30:23
toc : true
---

## 1. member1 변수를 JSON 문자열로 변환한 후 다시 객체로 바꿔서 member2 변수에 저장하는 소스를 작성해 보세요.
<br>

```js
let member1 = {name: "도레미", age: 25}


[json 문자열 변환 후 객체 코드]

>> let member2 = JSON.parse(JSON.stringify(member1));


```
​

<br>

## 2. [실습] JSON 자료를 가져와 표시하기 1
<br>

```js
[코드]

let xhr = new XMLHttpRequest();
xhr.open('GET', 'student.json', true);
xhr.send();

xhr.onreadystatechange = function () {
  if (xhr.readyState === 4 && xhr.status === 200) {
    let student = JSON.parse(xhr.responseText);
    document.getElementById('result').innerHTML = `
            <h1>${student.name}</h1>
            <ul>
              <li>전공 : ${student.major}</li>
              <li>학년 : ${student.grade}</li>
            </ul>
        `;
  }
};

```
​

[결과]

​![test1](https://github.com/leejieun9/leejieun9.github.io/blob/master/docs/assets/images/12-3.PNG?raw=true)

<br>
​

​
<br>

## 3. [실습] JSON 자료를 가져와 표시하기 2

```js
[코드]

​let xhr = new XMLHttpRequest();
xhr.open("GET", "student-2.json");
xhr.send();

xhr.onreadystatechange = function () {
  if (xhr.readyState === 4 && xhr.status === 200) {
    let students = JSON.parse(xhr.responseText);
    renderHTML(students);
  }
};


```
​

​

## 4. 서버에 있는 JSON 자료를 가져와서 화면에 표시하려 합니다. JSON 자료에는 id를 비롯해 여러 개의 값이 담겨 있습니다. 앞에서 공부한 XMLHttpRequest 객체를 사용해 자료를 가져와서 상품 이름과 생산 연도를 화면에 표시해 보세요.


JSON 자료위치: reqres.in/api/products/10

​

사용할 파일

- 12\quiz-1.html  

​

힌트

> 먼저 서버에 있는 JSON 자료의 위치를 변수에 저장한다.

> XMLHttpRequest 객체를 사용해 앞에서 지정한 주소에서 자료를 가져온다.

> 서버에서 JSON 자료를 가져오는데 성공했는 지 체크한다.

> 성공했다면 가져온 JSON 자료를 객체로 변환한다.

> 객체 안의 정보 중에서 상품 이름과 생산 연도를 가져와서 화면에 표시한다.

​
```js

[코드]

​<script>
    let xhr = new XMLHttpRequest();
    xhr.open("GET", "https://reqres.in/api/products/10");
    xhr.send();

    function renderHTML(contents){
      let output = `
        <p>상품명: ${contents.data.name}</p>
        <p>학년: ${contents.data.year}</p>
      `;
      
    document.querySelector("#result").innerHTML = output;


    }

    xhr.onreadystatechange = function() {
    if (xhr.readyState == 4 && xhr.status == 200) {
        let students = JSON.parse(xhr.responseText);
        renderHTML(students);
      }
    }

  </script>


```

[결과]

​![test1](https://github.com/leejieun9/leejieun9.github.io/blob/master/docs/assets/images/12-1.PNG?raw=true)

<br>

## 5. 12\quiz-2.html 문서에는 10보다 작은 수를 입력하는 텍스트 필드가 있습니다. 사용자가 숫자를 입력한 후 [입력] 버튼을 클릭했을 때 10보다 작은 수이면 화면에 표시하고, 10보다 큰 수를 입력했거나 아무 값도 입력하지 않았을 때, 또는 숫자가 아닌 다른 내용을 입력했을 때 예외를 처리하는 소스를 작성해 보세요.

​

사용할 파일

- 12\quiz-2.html  

​

힌트

> 텍스트 필드에 입력한 값을 가져와서 변수로 저장한다.

> try 블록에서는 가져온 입력값에 따라 어떻게 동작할 지를 작성한다.

> catch 블록에서는 알림 창에 error 개체를 표시한다.

> finally 블록에서는 다음 입력을 위해 텍스트 필드를 지운다.

​
```js
[코드]

​<script>
    const bttn = document.querySelector("button");
    bttn.addEventListener("click", function() {
      let value = document.querySelector("#user-number").value;
      try{
        let num = parseInt(value);
        if(num < 10){
          document.querySelector("#result").innerHTML = num;
        }else if(num >= 10){
         throw "10보다 작은 수를 입력하세요";
        }else{
          throw "숫자를 입력하세요";
        }
      }catch(error){
        alert(error);
      }
    });
    
  </script>

```

[결과]

​![test1](https://github.com/leejieun9/leejieun9.github.io/blob/master/docs/assets/images/12-2.PNG?raw=true)
