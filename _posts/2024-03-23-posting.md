---
categories: JavaScripts
title: "자바스크립트 4장 함수와 스코프 연습문제"
date: 2024-03-23 00:23:03
toc : true
---

## 문제1번

## 1. 두 수를 받아서 곱하고 결괏값을 반환하는 함수를 만든 후 10과 20을 곱한 결괏값을 콘솔 창에 표시하는 코드를 작성하시오.
<br>

```js
function calc(a,b){
  let result = a*b;
  console.log(`두 수의 곱: ${result}`);
}
calc(10,20);
```

<br>
<br>
<br>

## 문제 2번

### 2.화살표 함수를 사용해 두 수를 받아서 곱하는 함수를 정의한 후, 10과 20을 곱한 결괏값을 콘솔 창에 표시하시오.

```js
 let mul = (a,b) => a*b;
console.log(`10*20 = ${mul(10,20)}`);
  ```

<br>
<br>
<br>
<br>


## 문제 3번

## 3.콜백 함수를 이용해 사용자 이름과 나이를 입력하면 알림 창에 ‘안녕하세요? OOO님, 나이가 OO이군요.’라고 출력하는 코드를 작성하시오 <br>
 
  ```js
  function showData(name, age){
  alert(`안녕하세요 ${name}님, 나이가 ${age}세시군요.` )
}
function getData(callback){
  let userName = prompt("이름 입력하세요");
  let userAge = prompt("나이를 입력하세요");

  callback(userName,userAge);
}
getData(showData);
```
  
## 문제4번

## 4.다음 소스 코드를 실행하면 콘솔 창에 어떤 내용이 표시될 지 예상해 보시오. <br>

```js
const user = ["His", "name", "is", "Hong"];
console.log(user);
console.log(...user);
```
첫번째 결과값>> <span style="color: blue;">['His', 'name', 'is', 'Hong']</span>

<br>

두번째 결과값>> <span style="color: blue;">[His name is Hong]</span>
<br>
<br>
<br>

## 문제5번

## 5.사용자가 프롬프트 창에 숫자를 입력했을 때 그 숫자를 함수로 넘겨주고, <br> 
*함수에서는 숫자가 양수인지, 음수인지, 또는 0인지 판단해서 알림 창에 보여주는 프로그램을 작성하시오.*
<br>

```js
function Whatint(n){
  if (n > 0) {
    alert(`${n}은 양수입니다.`);
  } else if (n < 0) {
    alert(`${n}은 음수입니다.`);
  } else {
    alert(`${n}은 0입니다.`);
  }
}
const number = parseInt(prompt("숫자를 입력하세요"));

if(!isNaN(number)){
  Whatint(number);
}
```
<br>

## 문제6번

## 6. 2개의 숫자를 입력받아 두 수의 최대공약수를 구하는 함수를 작성하고 테스트해 보시오. <br>
*예를 들어 4와 12의 최대공약수는 4이다. 즉, 두 수 모두 나누어 떨어지는 수 중에서 가장 큰 값이 최대 공약수이다.*
<br>

<span style="color: red;">힌트</span>
>1. 주어진 두 수 중에서 어떤 수가 큰 수인지 확인한다.<br>

>2. 두 수가 모두 나누어 떨어져야 하므로 두 수 중에서 큰 수까지 반복하면서 작은 수도 나누어 떨어지고, 큰 수도 나누어 떨어지는 수를 찾는다.<br>

>3. 찾을 때마다 변수에 할당한다. 반복이 모두 끝나면 변수에는 가장 마지막에 할당한 약수만 남는다.<br>

```js
function quiz2(num1,num2){
  if(num1 > num2){
    max = num1;
  }else{
    max = num2;
  }

  for(let i=1;i<=max;i++){
    if(num1%i==0 && num2%i==0){
        result = i
    }
  }
  return result;
}


let num1 = prompt("첫번째 숫자를 입력하세요");
let num2 = prompt("두번째 숫자를 입력하세요");
let result = 0;
alert(`${num1}과 ${num2}의 최대공약수 : ${quiz2(num1, num2)}`);

```
<br>
<br>
