---
categories: JavaScripts
title: " 자바스크립트 3장 연산자와 제어문 과제"
date: 2024-03-20 00:23:03
toc : true
---
 
***
ㅎ..ㅎ 전 포스팅을 보다보니 뭔가 짜증이 솟구쳐서 안되겠다..때론 바야흐로 저번주에...ㅋㅋㅋ
  <br>
  <br>
어쩌다보니 주4일 연속근무를 하게되었는데 맨날 무거운거 들고다니고 얼음푸고 버거만들고 그러다보니
손목이 너덜너덜 해 질때쯤

일요일 12시부터 1시까지 런치피크가 터져버림....젠장...

 (한시간에 배달 50개 언저리 정도?)


배달 잡았는데 아직 초보라 어렵고 햇갈리는데 음료도 내가하고 커피 아이스크림까지 아무도 안도와주는 것이다.
(눈물) <br>

![test1](https://github.com/leejieun9/leejieun9.github.io/blob/master/docs/assets/images/1-1.PNG?raw=true)

그리고 한명 출근해서 음료랑 해주겠다고 한명을 뒀는데 한가지 문제가 생겼다.....
  <br> .
  <br> .
  <br> .
그것은 바로
  <br> .
  <br> .
  <br> . 
  <br> .
  <br> .
  <br> .
  <br> .
  <br> . 
  <br> .
  <br> .
  
그 친구가 새로들어온지 한달 되었다는 점이었다.
손이 정말 느렸는데 도와주려고 어디부터 해야하냐고 물었을때 모른다고 나한테 역질문을 하는 것이었다.
## 어?
![test1](https://github.com/leejieun9/leejieun9.github.io/blob/master/docs/assets/images/1-5.PNG?raw=true)

진짜 딱 이 표정이었다.

매니저님들은 음료 달라고 내 이름만 부르시니.......커버치면서 배달돌리느라 멘탈이 나갔다.
~~새크루 너 밤길 조심해라~~

  <br>
  <br>
  
그렇다. 그게 바로 내 손목이 죽은 이유다.. 

바로 파스붙이고 보호대 차고 집오자마자 기절하느라 과제를 못했다


암튼..그렇다....


![test1](https://github.com/leejieun9/leejieun9.github.io/blob/master/docs/assets/images/1-4.PNG?raw=true)


 ~~아무도 뭐라 안했지만 암튼 억울해서 써봤다. 여기에서라도 한풀이 해야지~~

 
암튼 내 썰풀이는 여기까지고 더 이상 미루면 큰일날거 같은 이 과제를 먼저 끝내보자
***

## 문제1번

## 1. 다음 프로그램의 실행 결과를 예측해 보시오. <br>
```js
console.log(2 + 2 - 2 * 2 / 2 * 2);
console.log(2 - 2 + 2 / 2 * 2 + 2);
```
<br>
<br>
<br>
첫번째줄 순서) `/` -> `*` -> `*` -> `+` , `-` = 0 <br>
두번째줄 순서) `/` -> `*` -> `-` , `+` = 4 <br>
<br>

## 문제 2번

## 2. 다음 코드의 실행 결과를 적으시오.

```js
  const number = 10;

  console.log(number++);
  console.log(++number);
  ```

<br>
<br>
<br>

 <span style="color: red;"> 에러에러~~ </span>


![test1](https://github.com/leejieun9/leejieun9.github.io/blob/master/docs/assets/images/1-3.PNG?raw=true)


let number를 선언한다면 "11"이 나온다.
<br>
<br>


## 문제 3번

## 3. 다음의 표현식이 false와 true로 나오는 이유를 설명하시오. <br>
```js

"A" > "B"                        // false
"Javascript" > "JAVASCRIPT"      // true
```
<br>
<br>
<br>
아스키코드 값이 있기때문에 다르게 나온다.
<br>
<br>
  
## 문제4번

## 4. 다음 코드의 주석 부분에 변수 x, y의 값을 표에 있는 값과 같이 할당할 때 <br>
**나오는 출력 결과를 쓰시오.** <br>
```js
let x, y;

if (x > 4) {
    if (y > 2) {
        console.log(x * y);
    }
} else {
    console.log();
}
```


| 입력값               | 결과값         | 해설
|:---------------------|:---------------|:---------------------------------------
| x = 2, y = 10        |                | x 값 조건 X 
| x = 1, y = 4         |                | x 값 조건 X
| x = 10, y = 2        |                | y 값이 조건 X 

<br>
<br>

## 문제5번

## 5. 다음의 중첩 조건문을 논리 연산자를 사용해 하나의 if 조건문으로 작성하시오.
<br>
```js
if (x > 10) {
    if (y > 20) {
        console.log("조건에 맞습니다.");
    }
}
```
  
```js
if( x > 10 && y > 20) console.log("조건에 맞습니다.");
```
<br>
<br>

## 문제6번

## 6. 다음과 같이 if 문으로 작성된 코드를 swith 문으로 바꾸시오.
<br>

```js
// 학년 변수를 생성한다.
let level = 1;

// 출력한다.
if (level == 1) {
    console.log("수강해야 하는 전공 학점: 12학점");
} else if (level == 2) {
    console.log("수강해야 하는 전공 학점: 18학점");
} else if (level == 3) {
    console.log("수강해야 하는 전공 학점: 10학점");
} else if (level == 4) {
    console.log("수강해야 하는 전공 학점: 18학점");
}

```


```js
// 학년 변수를 생성한다.
let level = 1;

// 출력한다.
switch (level) {
  case 1:
    console.log("수강해야 하는 전공 학점: 12학점");
  case 2: 
    console.log("수강해야 하는 전공 학점: 18학점");
  case 3:
    console.log("수강해야 하는 전공 학점: 10학점");
  case 4:
    console.log("수강해야 하는 전공 학점: 18학점");
}
```
<br>
<br>

## 문제7번
___

## ​7. 다음 프로그램의 실행 결과를 예측해 보시오.
```js
const array = ['사과', '배', '귤', '바나나'];

console.log('# for in 반복문');
for (const i in array) {
    console.log(i);
}

console.log('# for of 반복문');
for (const i of array) {
    console.log(i);
}
```

  in 반복문은 0 1 2 3, of 반복문 `사과 배 귤 바나나
<br>
<br>

## 문제8번

**8번. ​사용자로부터 숫자 2개를 입력받아 첫 번째 입력받은 숫자가 큰 지, 두 번째 입력받은 숫자가 큰지를**<br>
**구하는 프로그램을 작성하시오.** <br>


  ```js
  const one = prompt("첫번째 숫자를 입력하세요");
  const two = prompt("두번째 숫자를 입력하세요");

  if(one > two){
    console.log("첫번째 숫자가 더 큽니다.");
  }else if(one < two){
    console.log("두번째 숫자가 더 큽니다.");
  }else{
    console.log("둘다 같습니다.");
  }
  ```
<br>
<br>

## 문제9번

## ​​9.사용자로부터 숫자를 입력받아 양수, 0, 음수를 구분하는 프로그램을 작성하시오.

  
  ```js
  const n = prompt("숫자를 입력하세요");

  if(n>0){
    console.log("양수입니다.");
  }else if(n<0){
    console.log("음수입니다.");
  }else if(n==0){
    console.log("0입니다.");
  }
  ```
<br>
<br>

## 문제10번

## 10. 사용자로부터 월을 입력받아 무슨 계절인지 출력하는 프로그램을 작성하시오.


  ```js
  const n = prompt("월(달)를 입력하세요");

  if(n==12 || n==1 || n==2){
    console.log(`${n}월은 겨울`);
  }else if(n==3 || n==4 || n==5){
    console.log(`${n}월은 봄`);
  }else if(n==6 || n==7 || n==8){
    console.log(`${n}월은 여름`);
  }else if(n==9 || n==10 || n==11){
    console.log(`${n}월은 가을`);
  }
  ```
<br>
<br>

## 문제11번

## 11. 다음 프로그램에서 같은 결과가 나오도록  for of 문을 for in  문으로 바꾸시오. 

```js
let array = [52, 273, 32, 93, 103];

for (let element of array) {
    console.log(element);
}
```

  
  ```js
let array = [52, 273, 32, 93, 103];

for (let element in array) {
    console.log(array[element]);
}
```
<br>
<br>

## 문제12번


## 12. 1부터 100까지 숫자를 곱하는 프로그램을 작성하시오.  

  ```js
  let sum = 1;

  for(let i=1;i<=100;i++){
      sum = sum*i;
  }
  console.log(s);
  ```
<br>
<br>

## 문제13번


## 13. 숫자 1부터 999까지 짝수가 몇 개인지 출력하는 프로그램을 작성하시오. <br>

<br>
  
  ```js
  let cnt = 0;

  for(let i=1;i<=999;i++){
      cnt++;
  }
  console.log(cnt);
  ```
<br>
<br>
