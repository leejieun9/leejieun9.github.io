---
categories: JavaScripts
title: " 자바스크립트 3장 연산자와 제어문 연습문제"
date: 2024-03-19 00:23:03
toc : true
---

***
지각이다. 변명꺼리는 많지만 하지않겠다..근황은 손목이 아작났다. 변명에 그 이유도 존재하지만 ....휴 시작하자

***
 

## 문제 1번

### 1. 자신의 나이를 age 변수에 저장한 후 콘솔 창에 '나는 OO세입니다.'라고 출력하는 코드를 작성하시오.

```js
//file : main.js

  let age = 22;
  console.log("나는 "+age+"세입니다.")
```
age 변수에 내 나이를 저장하고 콘솔창 출력을 하는 코드를 쓰면 된다.

~~22살은 내 나이가 아니다 아니였음 좋겠다.~~

## 문제 2번
### 5개 색깔 red, blue, green, white, black 을 colors라는 배열에 저장한 후 for문을 이용해 화면에 표시하는 코드를 작성하시오.

```js
//file : main1.js

  const colors = ["red","blue","green","white","black"]; 
  for(let i = 0; i <colors.length;i++){
    document.write(`${colors[i]}. `);
  } 

```
컬러에 배열을 써서 값을 나열하고 길이만큼 돌고 순서대로 값이 출력되게 만드는 코드다.

for문 또는 foreach문도 쓰기도한다.

~~차이점은 알아서 알아보자~~

## 문제 3번
### "짝수와 홀수를 구별하는 프로그램 만들기” 실습을 수행하고, 결과를 첨부하시오

실습 따라하기라서 딱히 코드를 올릴필요는 없지만 나는 친절하니까(?) 같이 올린다.
```js
//file : ex.js

let userNumber = prompt("숫자를 입력하세요");

if ( userNumber !== null) {
  userNumber = parseInt(userNumber); 
  (userNumber % 2 === 0) ? alert (`${userNumber} : 짝수`) :  alert(`${userNumber} : 홀수`);  
} 
```
![test1](https://github.com/leejieun9/leejieun9.github.io/blob/master/docs/assets/images/3-1.PNG?raw=true)


![test2](https://github.com/leejieun9/leejieun9.github.io/blob/master/docs/assets/images/3-2.PNG?raw=true)

## 문제 4번
### 5개 과일 apple, banana, cheery , grape, orange를 fruits라는 배열에 저장한 후 forEach 문을 이용해 화면에 표시하는 코드를 작성하시오

```js
//file : ex4.js

const fruits = ["apple","banana","cheery","grape","orange"];

fruits.forEach(function(fruit){
  document.write(`${fruit}.`)
});

```

## 문제 5번
### size 0.5, color 검정, type 볼펜 을 요소로 갖는 객체 pen을 만들고 for…in 문을 사용해 키와 값을 화면에 표시하는 코드를 작성하시오.

```js
//file : ex5.js

const pen = {
  size : 0.5,
  color : "검정",
  type : "볼펜"
}

for(key in pen){
  document.write(`${key}: ${pen[key]}<br>`);
}

```

## 문제 6번
###  교재 p.110에 있는 "소수인지의 여부 확인하기" 실습을 수행하고, 결과를 첨부하시오.

```js
//file : ex6.js

const number = parseInt(prompt("자연수를 입력하세요"));
let isPrime = true;

if (number === 1) {
  console.log(`1은 소수도 아니고 합성수도 아닙니다.`);
} else if (number === 2) {
  isPrime = true;   // 2는 소수이므로 true로 설정
} else {
  for (let i = 2; i < number; i++) {
    if (number % i === 0) {
      isPrime = false;
      break;
    }
  }
}

if (isPrime) {
  console.log(`${number}은 소수입니다.`);
} else {
  console.log(`${number}은 소수가 아닙니다.`);
}


```
<br>

![test3](https://github.com/leejieun9/leejieun9.github.io/blob/master/docs/assets/images/3-3.PNG?raw=true)

![test4](https://github.com/leejieun9/leejieun9.github.io/blob/master/docs/assets/images/3-4.PNG?raw=true)


<br>

## 문제 7번
### 03\quiz-1.html 문서에는 배열이 주어져 있다. 이 배열에서 10보다 큰 값을 찾아 화면에 표시하는 프로그램을 작성하시오

```js
//file : ex7.js
let Number = [1, 3, 5, 7, 9, 11, 13, 15, 17, 19];

for (let i=0; i< Number.length;i++ ){
  if(Number[i]>10){
    document.write(`${Number[i]}, `);
  }
}
```

## 문제 8번
### 사용자에게 1보다 큰 수를 입력하게 한 후 입력한 숫자까지 짝수만 더하는 프로그램을 작성하시오.

```js
//file : ex8.js

let userNumber = prompt("1보다 큰 슷자를 입력하세요");
// 1)만약 사용자가 "취소"버튼을 눌렀을 경우 null값을 가짐
// 2) 1보다 큰 수를 입력해야하므로
let sum = 0;
if(userNumber !== null && userNumber>1){
  for( let i=1; i<=userNumber; i++){
    if(i%2==0){
      sum+=i;
      document.write(`${i} ------------ ${sum} <br> `);
    }
  }
}else{
  //조건식에 부합하지 않을 경우 해당 문구 결과를 출력
  alert("잘못 입력하셨습니다. 1보다 큰 수를 입력해주세요") 
}


```
사용자가 취소 버튼을 누르면 null 값을 가져야하고 1보다 큰수를 입력 합니다.



