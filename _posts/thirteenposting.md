---
categories: JavaScripts
title: " 자바스크립트 9장 자바스크립트 객체 보고서"
date: 2024-04-21 22:09:03
toc: true
---

## 문제1번

### 1. book1 객체에 책을 읽는 중인지 알려주는 done이라는 프로퍼티를 추가하시오.값은 true나 false 중에 선택하면 된다.

```js
book1.done = true
or
book1["done"] = true
```

<br>
<br>
<br>
<br>

## 문제 2번

### 2. [실습] 생성자 함수와 클래스를 사용해 원기둥 부피 구하기
<br>
<br>

```js
class Cylinder {
  constructor(cylinderDiameter, cylinderHeight) {
    this.diameter = cylinderDiameter;
    this.height = cylinderHeight;
  }
  volume() {
    let radius = this.diameter / 2;
    return (Math.PI * radius * radius * this.height).toFixed(2); 
  }
}

// let cylinder = new Cylinder(8, 10);   
// console.log(`원기둥의 부피는 ${cylinder.volume()}입니다.`);   

const button = document.querySelector("button"); // 계산하기 버튼 생성성
const result = document.querySelector("#result"); // 결괏값 표시 영역

button.addEventListener("click", function (event) {
  event.preventDefault();
  const diameter = document.querySelector("#cyl-diameter").value; // 지름값
  const height = document.querySelector("#cyl-height").value; // 높잇값

  if (diameter === "" || height === "") {
    result.innerText = `지름값과 높잇값을 입력하세요.`;
  } else {
    let cylinder = new Cylinder(parseInt(diameter), parseInt(height)); // 인스턴스 생성
    result.innerText = `원기둥의 부피는 ${cylinder.volume()}입니다.`; // 부피 계산해서 result 영역에 표시
  }
});
```
![test1](https://github.com/leejieun9/leejieun9.github.io/blob/master/docs/assets/images/9-1.PNG?raw=true)

<br>
<br>

## 문제 3번

### 3. [실습] 프로토타입을 상속하는 새로운 객체 만들기


```js
function Book (title, price) {
  this.title = title;
  this.price = price;
}

Book.prototype.buy = function() {
  console.log(`${this.title}을(를) ${this.price}원에 구매하였습니다.`);  
}

const book1 = new Book("ABCDE", 10000);   
book1.buy();  // Book 객체의 buy() 메서드 사용

// 기존 객체를 확장해서 새로운 객체 만들기
function Textbook(title, price, major) {
  Book.call(this, title, price);   // 기존 객체의 프로퍼티 재사용
  this.major = major;               // 새로운 프로퍼티 정의
}

Textbook.prototype.buyTextbook = function() {   // 새로운 메서드 정의
  console.log(`${this.major} 전공 서적, ${this.title}을 구매했습니다.`);
}

Object.setPrototypeOf(Textbook.prototype, Book.prototype);   // Textbook 프로토타입을 Book 프로토타입으로 연결

const book2 = new Textbook("알고리즘", 5000, "컴퓨터공학");
book2.buyTextbook();     // Textbook 객체의 메서드 사용
book2.buy();             // Book 객체의 메서드 사용

```
## 문제 4번

### 4.[실습] 클래스 상속 연습하기

```js
class BookC  {
  constructor(title, price) {
    this.title = title;
    this.price = price; 
  }
  buy() {
    console.log(`${this.title}을(를) ${this.price}원에 구매하였습니다.`);  
  }
}

const book1 = new BookC("자료 구조", 15000);
book1.buy();

// 기존 클래스를 확장해서 새로운 클래스 선언하기
class TextbookC extends BookC {
  constructor(title, price, major) {
    super(title, price);   // 기존 클래스의 프로퍼티 재사용
    this.major = major;     // 새로운 프로퍼티 정의
  }

  buyTextbook () {   // 새로운 메서드 정의
    console.log(`${this.major} 전공 서적, ${this.title}을 구매했습니다.`);
  }
}

const book2 = new TextbookC("인공지능", 5000, "컴퓨터공학");
book2.buyTextbook();
book2.buy();
```

<br>
<br>
<br>
<br>
<br>

## 문제5번

### 5. Pet 클래스를 만든 후 인스턴스 객체를 만들어 보세요. 이때 Pet 클래스는 name과 color 프로퍼티, run() 메서드를 가지고 있습니다.
*그리고 run() 메서드는 반려동물의 이름과 함께 'is running.'이라는 문자열을 알림 창에 표시하도록 정의합니다.*
```js
<script>
  class Pet{
    constructor(name,color){
      this.name = name;
      this.color = color;
    }
    run() {
      alert(`${this.name} is running`);
    }
  }

  let myPet = new Pet("해리","베이지");
  myPet.run();
</script>
```
![test1](https://github.com/leejieun9/leejieun9.github.io/blob/master/docs/assets/images/9-2.PNG?raw=true)

<br>
<br>

## 문제6번

### 6. 5번에서 만들었던 Pet 클래스를 상속받는 Cat 클래스를 만들어 보세요.
*이때 Cat 클래스에는 고양이 품종을 나타내는 breed라는 프로퍼티를 추가하고 객체의 이름과 색상, 품종을 표시하는 viewInfo() 메서드도 추가합니다.*
*그리고 Cat 클래스의 인스턴스를 만들고 인스턴스 객체에서 viewInfo() 메서드를 실행해 보세요.*

```js
 <script>
  class Pet{
    constructor(name,color){
      this.name = name;
      this.color = color;
    }
    run() {
      alert(`${this.name} is running`);
    }
  }

  // let myPet = new Pet("온유","초록색");
  // myPet.run();

  class Cat extends Pet{
      constructor(name, color, bread){
        super(name, color);
        this.breed = bread;
      }
      viewInfo() {
        alert(`이름: ${this.name}, 품종: ${this.breed}, 색상: ${this.color}`);
      }
    }
    let myCat = new Cat("고양이","삼색","삼색고양이");
    myCat.viewInfo();
</script>
```
![test1](https://github.com/leejieun9/leejieun9.github.io/blob/master/docs/assets/images/9-3.PNG?raw=true)
