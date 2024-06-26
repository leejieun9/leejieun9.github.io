---
categories: JavaScripts
title: " 자바스크립트 4장 함수와 스코프 과제"
date: 2024-03-24 00:23:03
toc : true
---

***
하하 지금 굉장히 과제에 치이고있다 지금 현재 다음주 시험이고 시험범위는 7장까지이다 어라..? 난 이제 4장인데...
발에 불 떨어진 수준이 아니라 번개가 쳤다...이젠 미룰 수 없다....

***
<br>

## 문제1번

## 1. 다음 중 코드에서 사용한 함수 정의 방법을 모두 고르세요. <br>
```js
const add = function(){};

① 함수 표현식

② 함수 선언문

③ 화살표 함수

④ 네이밍 함수

⑤ 익명 함수
```

해설:정답은? 1번

함수 표현식- 함수 리터럴을 사용하여 함수를 값으로 정의하는 문법 <br>
화살표 함수 - 함수 표현식의 간결한 형태 매개변수와 함수 본문을 화살표로 구분하여 정의 ex)(변수) =>{함수} <br>
네이밍 함수 - 함수 이름과 동일한 이름으로 매개변수를 지정하여 사용하는 함수 <br>
익명 함수 - 함수 이름 없이 매개변수와 함수 본문만으로 구성된 함수<br>
함수 선언문- function 키워드 사용하여 함수 정의 하는 문법<br>


## 문제 2번

## 2. 코드에서 max 변수의 출력값이 배열 중 가장 큰 숫자가 될 수 있도록 getArrayNumber() 함수를 완성하세요. <br>
*이때, 배열 요소는 반드시 숫자형이라고 가정합니다.*


```js
  function getArrayMaxNumber(arr){ 
    /* 함수 코드를 완성하세요 */ 
}
const max = getArrayMaxNumber([10, 50, 30]);
console.log(max); 

```
```js
function getArrayMaxNumber(arr){ 
    let max = arr[0]; 
    for(let i=0;i<arr.length;i++){
        if(arr[i]>max){
            max = arr[i];
        }
    }
    return max;
}
const max = getArrayMaxNumber([10, 50, 30]);
console.log(max);
```
<br>
<br>
<br>

## 문제 3번

## 3. 다음 중 코드를 실행했을 때 콘솔창에 출력될 값을 고르세요.
```js

var text = "outside";
function printScope(){
  console.log(text);
  var text = "inside";
};
printScope();
```
① outside

② inside

③ null

④ undefined

⑤ " "

**[해설]- 정답은? 4번**
<br>
함수 내에서 변수를 선언하고 값을 할당하기 전에 해당 변수를 사용하게 되면 초기화되기때문에
<br>
text변수에 값을 할당하기 전에 콘솔 실행하면 초기화되서 undefined 출력이 됨!!
<br>
<br>
  
## 문제4번

## 4. 다음 코드를 실행하면 출력될 변수 result의 값을 고르세요. <br>
```js
const result = (function(a, b){
  function init(){
    return doSum(a, b);
  }
  function doSum(a, b){
    return a + b;
  }
  return init();
})(10, 20);
console.log(result);

```

① undefined

② null

③ 50

④ 30

⑤ SyntaxError

**해설: 정답은? 4번**

'init' 함수는 함수의 반환 값을 받게되고 'dosum' 함수를 호출해서 그 결과롤 반환하기 때문에 <br>
'result' 변수에는 30을 출력하기 때문에 4번!

<br>
<br>

## 문제5번

## 5.원의 넓이를 구하는 공식은 (반지름) × (반지름) × (원주율)입니다. 
*원주율은 3.14라고 했을 때, 원의 반지름을 이용해 원의 넓이를 반환하는 함수를 만들어 보세요.*

콘솔 출력) 반지름 ○인 원의 넓이는 □ □ □입니다.

<br>
```js
function Circle(radius) {
    const pi = 3.14;
    const s = pi * radius * radius;
    return s;
}

const radius = prompt("반지름 입력하세요"); // 반지름
const s = Circle(radius); // 원의 넓이
console.log(`반지름 ${radius}인 원의 넓이는 ${s}입니다.`);


```
<br>
<br>

## 문제6번

## 6. 매개변수로 배열을 전달받아 배열의 요소 중에서 가장 큰 수를 찾아 반환하는 함수를 만들어 보세요. <br>
*이때, 배열 안의 데이터는 모두 0보다 큰 정수라고 가정합니다.* <br>
> *테스트 배열: [10, 20, 50, 5, 30]* <br>
> *콘솔 출력) 가장 큰 수는 50입니다.*
<br>

```js
function Number(arr) {
    let max = arr[0]; 
    
    for (let i = 0; i < arr.length; i++) {
        if (arr[i] > max) {
            max = arr[i]; 
        }
    }
    return max; // 최대값 반환
}

const testArray = [10, 20, 50, 5, 30];
const MaxNumber = Number(testArray);
console.log(`가장 큰 수는 ${MaxNumber}입니다.`);

```
<br>

## 문제7번
___

## ​7. 체질량 지수(BMI)를 계산하는 공식은 몸무게를 키(m)의 제곱으로 나눈 값입니다.
*사용자에게 키(cm)와 몸무게(kg)에 해당하는 값을 전달받아 체질량 지수를 계산합니다.*
*체질량 지수가 26점 이상이면 비만, 24~25점은 과체중, 18.5~23점은 정상, 18.5점 미만은 저체중을 반환하는 함수를 만들어 보세요.*

```js
ex)

테스트 #1) 키: 180cm, 몸무게: 100kg → 콘솔출력: 비만

테스트 #2) 키: 180cm, 몸무게:   80kg → 콘솔출력: 과체중

테스트 #3) 키: 180cm, 몸무게:   70kg →콘솔 출력: 정상

테스트 #4) 키: 180cm, 몸무게:   59kg → 콘솔출력: 저체중

```

```js
function BMI(height, weight) {
    const heightMeter = height / 100; // cm -> m 변환
    const bmi = weight / (heightMeter * heightMeter); // bmi

    if (bmi >= 26) {
        return "비만";
    } else if (bmi >= 24 && bmi <= 25) {
        return "과체중";
    } else if (bmi >= 18.5 && bmi <= 23) {
        return "정상";
    } else {
        return "저체중";
    }
}

// 입력 받고 값 출력
let height = prompt("키 입력하세요");
let weight = prompt("몸무게 입력하세요");
console.log(`키: ${height}cm, 몸무게: ${height}kg 은 ${BMI(height, weight)}`);

```
<br>
<br>


후기 - ~~헉 너무 어려운데..?~~
