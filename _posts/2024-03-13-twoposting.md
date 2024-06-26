---
categories: JavaScripts
title: " 자바스크립트 2장 변수 자료형 연습문제"
date: 2024-03-13 00:23:03
toc : true
---

***

과제를 다 하고 살펴보니 연습문제가 남아있었다..

모두들 연습문제를 열심히 풀고있었는데 나만 과제를 한것이다 (멘붕)

연습문제를 먼저했어야 했는데 과제부터 하니까 어렵지 😂😂

연습문제로 뒷북 쳐봅시다 둥둥둥

![test](https://github.com/leejieun9/leejieun9.github.io/blob/master/docs/assets/images/2-1.PNG?raw=true)

***
 

### 1. 알림창에 자신의 이름을 출력하는 코드를 작성해 보시오.

 ```js
// file: 02_ex.js
console.log("이지은")

```
<br>

### 2. 다음의 코드를 실행하여 나오는 '확인 창'에서 [확인] 버튼을 클릭했을 때 반환되는 값은 무엇인가?

```js
확인 누르면  True 로 취소 누르면 false로 나옵니다.
```
<br>

### 3. 콘솔 창에 '자바스크립트를 좋아합니다'라고 출력하는 코드를 작성해 보시오. <br>
```js
console.log("자바스크립트를 좋아합니다")
```
<br>

### 4. 변수 name을 선언해서 자신의 이름을 할당하고, 콘솔 창에 '나는 OOO입니다.'라고 출력하는 코드를 작성하시오. <br>
```js
let name = "자신의 이름";
console.log("나는 " + name + "입니다.");
```

<br>

### 5. number 변수값에 100을 더한 후 result 변수에 할당하는 코드를 작성하시오. <br>
```js
result = number + 100
```

<br>

### 6. prompt 문을 사용해 사용자 이름을 입력 받은 후 userName 변수에 저장하고, 템플릿 리터럴을 사용해 'OOO님, 반갑습니다!' 라고 콘솔창에 출력하는 코드를 작성하시오. <br>
*여기서 OOO에는 앞서 입력받은 사용자 이름이 들어가야 한다.*
```js
let userName = prompt("이름을 입력하세요.");
console.log("안녕하세요, " + userName + "님!");
```

<br>

### 7. '바나나', '사과', '포도'라는 값이 들어 있는 fruits 라는 배열을 선언하고, 배열에서 두 번째 값을 콘솔 창에 출력하는 코드를 작성하시오 <br>
```js
let fruits = ["바나나", "사과", "포도"];
console.log(fruits[1]);
```
<br>

### 8. name, age, gender라는 키를 가지고 있는 person이라는 객체를 만드는 코드를 작성하시오. 각 키의 값에는 자신에 해당하는 값을 넣으시오. <br>
```js
let person = {
  name: "홍길동",
  age: 30,
  gender: "남성"
};
```
<br>

### 9. 교재 80페이지에 있는 화씨 온도를 섭씨 온도로 변환하기 실습을 따라해서 결과 화면을 첨부하시오. <br>
```js
let fahrenheit = prompt("화씨 온도를 입력하세요.");
let celsius = (fahrenheit - 32) * 5/9;
alert(celsius + "도 입니다.");
```
<br>
![test](https://github.com/leejieun9/leejieun9.github.io/blob/master/docs/assets/images/2.PNG?raw=true)


![test](https://github.com/leejieun9/leejieun9.github.io/blob/master/docs/assets/images/1.PNG?raw=true)
<br>

![test](https://github.com/leejieun9/leejieun9.github.io/blob/master/docs/assets/images/4.PNG?raw=true)

<br>
![test](https://github.com/leejieun9/leejieun9.github.io/blob/master/docs/assets/images/3.PNG?raw=true)
<br>

### 10.  다음 표현식의 결과를 쓰시오. <br>

| 표현식 | 결과 | 해설 |
| --- | --- | --- |
| 4 + 10 | 14 | 정수 4와 10을 더한 결과로, 14가 출력됩니다. |
| 4 + "10" | 410 | 정수 4와 문자열 "10"을 더한 결과로, "410"이 출력됩니다. |
| "10" + 0.5 | 100.5 | 문자열 "10"과 0.5를 더한 결과로, "100.5"가 출력됩니다. |
| 10 + 0.5 | 10.5 | 숫자 10과 0.5를 더한 결과로, 10.5가 출력됩니다. |
| parseFloat("10" + 0.5) | 100.5 | 문자열 "10"과 0.5를 더한 결과로, "100.5"를 숫자로 변환한 후 출력됩니다.|

<br>

### 11. 사용자로부터 인치를 입력받아 센티미터로 바꾸는 프로그램을 작성하시오. 1인치는 2.54cm이다. <br>
```js
let inches = prompt("인치를 입력하세요:");
let centimeters = inches * 2.54;
alert(centimeters + "cm 입니다.");
```
<br>


