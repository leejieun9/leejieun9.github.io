---
categories: JavaScripts
title: " 자바스크립트 9장 자바스크립트 객체 과제"
date: 2024-04-23 22:10:23
toc: true
---

## 문제1번

### 1. 다음 코드를 실행한 후 마지막에 변수 studentObject에 할당된 객체의 키를 배열로 나열한 값을 고르세요.

```js
const studentObj = {
  name: "John",
  age: age,
};
studentObj.gender = "female";
delete studentObj.age;
```

<br>

➀ ['name', 'age', 'gender'] <br>

➁ ['age', 'gender'] <br>

➂ ['name', 'gender'] <br>

➃ ['name', 'age'] <br>

➄ ['age'] 
<br>
<br>
[정답]: 3번 <br>
<br>
<br>
`delete` 연산자를 호출하여 `studentObj` 객체의 `age` 속성이 삭제되었으므로, `studentObj`의 key는 `['name', 'gender']`입니다. 
<br>
<br>
<br>
<br>

## 문제 2번

### 2. 다음 중 obj 변수에 할당된 객체의 속성과 값이 다른 하나를 고르세요.

```js
➀  const obj = {name: "철수"}; <br>

➁ const obj = {}; <br>

    obj.name = "철수";
<br>
➂ const obj = {name: "철수", age: 20}; <br>
<br>
    delete obj.name; <br>

➃ const obj = {name: "영희"}; <br>

    obj.name = "철수"; <br>

➄ const obj = {}; <br>

    const obj2 = obj; <br>

    obj2.name = "철수"; <br>
```
<br>
<br>
[정답]: 2번 <br>
<br>
해설: `obj` 변수에 할당된 객체는 속성과 값이 모두 없는 빈 객체입니다. 다른 옵션들은 속성과 값이 있는 객체를 할당하거나 생성하는 예시입니다.

`const obj = {};`는 빈 객체를 생성하고, `obj.name`은 `undefined`를 반환합니다.

​
<br>
<br>

## 문제 3번

### 3. 자바스크립트에서 객체를 생성하는 키워드로 알맞은 것은?

➀  instance      ➁ object      ➂ new      ➃ create
<br>
<br>
<br>
[정답] : 3번
<br>
<br>
해설: 생성자 함수를 호출하여 새로운 객체를 생성할 때 사용됩니다.

<br>
<br>

## 문제 4번

### 4. 자바스크립트에서 키워드 this가 의미하는 것은? <br>

➀  현재 스크립트     ➁ 현재 문서      ➂ 현재 객체      ➃ 현재 브라우저
<br>
<br>
<br>
[정답] : 3번 현재 객체 <br>
<br>
<br>
해설: 메소드 내에서 'this' 는 해당 메소드가 속한 객체를 가리킵니다.
<br>
<br>

## 문제5번

### 5. 객체 dog에 color라는 속성을 저장하고자 한다. 올바르게 저장하는 문장은?

➀  dog.color = 'orange';     ➁ dog[color] = 'orange';     ➂ dog_color = 'orange';     ➃ let dog.color = 'orange';

[정답] : 1번 dog.color = 'orange'; <br>
<br>
<br>
<br>
해설: 객체의 속성은 점(dot) 연산자를 사용하여 설정할 수 있습니다.

<br>
<br>

## 문제6번

### 6. 사용자를 나타내는 객체를 생성하고자 한다. 객체는 아이디, 나이, 패스워드 속성을 가지고 있다. {kim, 20, 1234} 값을 이용해 객체 하나를 생성한 후 객체의 모든 속성을 웹 페이지에 출력하는 코드를 작성하시오. 

```js
[코드]

<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Document</title>
</head>
<body>
  <script>
    const user = {
  id: "kim",
  age: 20,
  password: 1234,
};
// 객체 속성 출력
console.log(user); // 출력: { id: 'kim', age: 20, password: 1234 }
    
// 웹 페이지에 출력
document.body.innerHTML += "<p>사용자 ID: " + user.id + "</p>";
document.body.innerHTML += "<p>나이: " + user.age + "</p>";
document.body.innerHTML += "<p>비밀번호: " + user.password + "</p>";

  </script>
</body>
</html>
```
[결과]

![test1](https://github.com/leejieun9/leejieun9.github.io/blob/master/docs/assets/images/9-4.PNG?raw=true)
