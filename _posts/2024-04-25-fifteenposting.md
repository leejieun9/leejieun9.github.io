---
categories: JavaScripts
title: " 10장 문자열과 배열 활용하기 과제"
date: 2024-04-25 00:00:02
toc: true
---

두둥 다시 열정이 생길시간~~

---

## 문제1번
<br>

###  1. 다음 배열에 대한 설명 중 틀린 것은?

```js
let months = new Array("Jan", "Feb", "March");
```

1) let months = ["Jan", "Feb", "March"]; 로 대신할 수 있다. <br>
> [] () 둘다 가능하다

2) months.length는 3이다.

3) months[1] = "Februray"; 코드는 "Feb"를 "Februray"로 수정한다.

4) months.length = 5로 지정하여 배열의 크기를 5개로 늘릴 수 없다.

    <span style="color:green"> **해설: 정답은 4번!** </span>

배열의 크기를 늘리려면 push()이라는 함수를 써야 늘릴 수 있다. <br>
 // months.push("April", "May", "June");

<br>
<br>

## 문제 2번

### 2.다음 배열에 대한 설명 중 틀린 것은?
```js
let grades = new Array("A", "B", "C", "D");
```

1) grades[4] = "F";를 실행하면 grades 배열의 크기가 1 늘어난다. <br>

2) grades[3[ = 70;은 잘못된 코드이다. 왜냐면 문자열 배열에 정수를 넣었기 때문이다. <br>

3) grades.reverse()를 호출한 결과 grades 배열 내부가 ["D", "C", "B", "A"]로 변한다. <br>

4) grades.length는 4이다.<br>

    <span style="color:green"> **해설: 정답은 1번!** </span>


 // `grades[4] = "F";`를 실행하면 JavaScript는 grades 배열에 새로운 요소를 추가하지 않고, 대신 grades[4]에 "F"를 할당합니다.


<br>
<br>
<br>


## 문제 3번

### 3. 주석에 맞게 다음 빈 칸을 채우시오.
```js
let ______________________________               // Array를 이용하여 크기가 3인 배열 money 생성 <br>
_____________________________ = 5;               // money의 첫 번째 요소에 5 삽입 <br>
_____________________________ = 7;               // money의 첫 번째 요소에 7 삽입 <br>
_____________________________ = -3;              // money의 첫 번째 요소에 -3 삽입 <br>
let sum = 0; <br>
for (let i=0; i<_______________; i++) sum += money[i];     // 배열 합 구하기<br>
document.write(________________);                // 평균 출력 <br>
```
<빈칸채우기>
```js
let money = Array(3);  // Array를 이용하여 크기가 3인 배열 money 생성 
    money [0]= 5;      // money의 첫 번째 요소에 5 삽입 
    money [1] = 7;      // money의 첫 번째 요소에 7 삽입 <br>
    money [2] = -3;     // money의 첫 번째 요소에 -3 삽입 <br>
let sum = 0; <br>
for (let i=0; i<money.length; i++) sum += money[i];     // 배열 합 구하기<br>
document.write(sum/money.length);                // 평균 출력 <br>
```
<br>
<br>
<br>

## 문제 4번

<br>

### 4. 다음의 자바 스크립트 코드가 있을 때 아래 각 항목의 실행 결과 변수 x의 값은 무엇인가?

**let text = "Web Programming";**

| 코드 | x값 |
| ---------- | ---------- |
|let x  = text.length;       | 14 |
|let x = text[2];          | e |
| let x = text.split(" ").length;  | 2 |  
|let x = text.replace("web", "HTML5");  | We Programming |
|let x = text.charAt(4);   | g |

## 문제 5번

### 5. prompt 함수를 호출하여 사용자로부터 문자열을 입력받고, "&" 문자를 기준으로 분할하여 출력하는 웹 페이지를 작성하시오.

[실행결과]

![test1](https://github.com/leejieun9/leejieun9.github.io/blob/master/docs/assets/images/10-2.PNG?raw=true)


[코드]
```js
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=<device-width>, initial-scale=1.0">
    <title>Document</title>
    <style>
        #container {
          width:500px;
          margin:20px auto;
        }
    </style>
</head>
<body>
    <div id="container">
        <h1>문자열 분할</h1>
        <ul id="result">

        </ul>
    </div>
    <script>
        // 이곳에 작성하세요
        var btn = document.getElementById("btn");
        btn.addEventListener("click", splitString);

        function splitString() {
            var input = prompt("문자열을 입력하세요:");
            var result = input.split("&");
            var ul = document.getElementById("result");
            for (var i = 0; i < result.length; i++) {
                var li = document.createElement("li");
                li.textContent = result[i];
                ul.appendChild(li);
            }
        }
    </script>
    
</body>
</html>
```
![test1](https://github.com/leejieun9/leejieun9.github.io/blob/master/docs/assets/images/10-3.PNG?raw=true)

![test1](https://github.com/leejieun9/leejieun9.github.io/blob/master/docs/assets/images/10-4.PNG?raw=true)
