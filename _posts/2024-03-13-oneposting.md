---
categories: JavaScript
title : 자바스크립트 2장 변수와 자료형
---
___

하하 벌써 개강이네요.....ㅎㅎ....처음배워보는 자바스크립트..비슷하겠죠..? 
이번에는 학기중에 과제 블로그를 끝내길...시작해봅시다
___

### 1. 다음 중 변수명으로 사용할 수 없는 것을 고르시오.
#### (1) a (2) hello (3) 10times (4) _ (5) $

 [해설] 정답 : 5번
 자바스크립트에서는 변수명은 알파벳, 숫자, 밑줄만 사용가능합니다.
 변수명은 알파벳이나 숫자로 시작해야 하고 영어(알파벳), 숫자, 밑줄만 사용할 수 있습니다.
 그러므로 5번 $는 변수명이 될 수 없습니다.


### 2. 변수 score를 선언해서 데이터 10을 할당하는 코드를 작성해 보시오.
```js
// file 2_0.html

const number = 10;
undefined
number
10
```
### 3. var와 let과의 차이, let과 const와의 차이를 간략하게 설명하시오.
[해설]  
var : 함수 스코프, 재할당 가능
함수 내에서 같은 이름의 변수가 여러 번 선언되어도 동일한 변수에 할당됩니다.

let : 블록 스코프, 재할당 가능
같은 이름의 변수가 블록 내에서 여러 번 선언되어도 각각 다른 변수에 할당됩니다.

const : 블록 스코프, 재할당 불가능
 같은 이름의 변수가 블록 내에서 여러 번 선언되어도 모두 에러가 발생합니다.

 ### 4. 다음 프로그램의 실행 결과를 예측해 보시오.
 ```js
console.log("\\\\\\\\");
```
콘솔에서 \ (백슬래시)문자 출력이고, 특수문자 (특수기호) 표시할때 사용합니다.
(백슬래시)두개에 하나가 나타나므로 \\\\가 출력될 것으로 예상합니다.

### 5. 다음 프로그램에서 오류를 찾아 고치시오.
```js
const r;
r = 10;
console.log(`넓이 = ${3.14 * r * r)`);
```
 출력하는 것을 보면 넓이 = 3.14 X 반지름 X 반지름 원의 넓이를 구하는데 별 오류가 없어보이지만 r 변수선언 하는 것 부터 잘못된 것 같다.  
 
 `r` 변수가 선언되기 전에 사용되었기 때문에 오류가 뜨는 것이고  const r = 10;으로 수정해야 원의 넓이를 계산 할 수 있다.
  
### 6. 다음 중 데이터의 종류와 자료형이 잘못 짝지어진 것을 고르시오.
<br>
(1) 문자열 - "Hello, Javascript"
<br>
(2) 숫자형 - 0.11121212
<br>
(3) 논리형 - true
<br>
(4) undefined - undefined
<br>
(5) 배열 - { }
<br>
해설: 답은 5번이다. 배열은 [] 대괄호 안에 나열해야하고, 쉼표로 구분한다.
<br>
<br>
### 7. 다음 코드의 실행 결과를 적으시오.<br>

| 코드 | 결과 | 해설 |
| --- | --- | --- |
| console.log(52 + 273); | 325 | 정수를 더한 결과로 325가 출력됩니다. |
| console.log("52" + 273); | 52273 | 문자열과 정수를 더한 결과로 52273이 출력됩니다. |
| console.log(52 + "273"); | 52273 | 정수와 문자열을 더한 결과로 52273이 출력됩니다. |
| console.log("52" + "273"); | 52273 | 문자열과 문자열을 더한 결과로 52273이 출력됩니다. |
| console.log(10 + 20 + "!!!!"); | 30!!!! | 정수, 정수, 문자열을 더한 결과로 30!!!!이 출력됩니다. |

<br>
<br>
### 8. 다음 프로그램의 실행 결과를 예측해 보시오.
<br>
<br>
 ```js
console.log("안녕하세요"[1]);
console.log("안녕하세요"[2]);
console.log("안녕하세요"[3]);
console.log("안녕하세요"[4]);
```
<br>
<br>
배열 순으로는 [0][1][2][3][4] 순 이기 때문에 녕하세요가 차례대로 결과가 나올 것입니다!

### 9. 사용자로부터 원의 반지름을 입력받아 원의 넓이와 둘레를 구하는 프로그램을 작성하시오.
<br>
 ( 참고: 원의 넓이 = 3.14 * r * r, 원의 둘레 = 2 * 3.14 * r )
 <br>
 <br>
 ```js
 let userInput = prompt("원의 반지름을 입력하세요:")
 let r = Number(userInput);
 let a = 3.14 * r * r;
 let b = 2 * 3.14 * r;

alert("원의 넓이는 " + a + "입니다.");
alert("원의 둘레는 " + b + "입니다.");
 ```
 r = 반지름  a = 넓이  b= 둘레로 선언하고 각자 계산하여 선언해준 코드입니다.

 
 그래도 전에 했던게 조금 도움이 되고있긴 하나봅니다. 조금 해맸지만 그래두 완성 더 어려워지지 말길..ㅜ