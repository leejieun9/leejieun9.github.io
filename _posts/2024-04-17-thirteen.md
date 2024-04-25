---
categories: JavaScripts
title: "자바 스크립트 8장 내장객체 보고서 (1)"
date: 2024-04-17 21:20:03
toc: true
---

## 문제1번

### 1. 자신의 생일을 사용해 Date 인스턴스를 만들고 birthDay라는 변수로 설정해 보세요.
<br>
```js
[코드] let birthday = new Date ("2003-10-23")
```
<br>

## 문제 2번

### 2. 만 보 걷기, 오늘까지 며칠째일까?

[코드]
```js
<!DOCTYPE html>
<html lang="ko">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>만보 걷기 - 오늘로 며칠째?</title>
  <link rel="stylesheet" href="css/main.css">
  <style>
    h1 {
      margin-bottom:20px;
    }
    #result {
      font-size:1.5em;
      font-weight: bold;
      color:red;
    }
  </style>
</head>
<body>
  <h1>만보 걷기</h1>
  <p><span id="result"></span>일 연속 달성</p>
  <script>
    const firstDay = new Date("2024-01-01");
    const today = new Date();
    let diff =  (today.getTime() - firstDay.getTime())/(24*60*60*1000);
    document.querySelector("#result").innerHTML = 
      Math.round (diff);
  </script>
</body>
</html>
```
### [스크립트 부분]
```js
<script>
    const firstDay = new Date("2024-01-01");
    const today = new Date();
    let diff =  (today.getTime() - firstDay.getTime())/(24*60*60*1000);
    document.querySelector("#result").innerHTML = 
      Math.round (diff);
  </script>
```
![test1](https://github.com/leejieun9/leejieun9.github.io/blob/master/docs/assets/images/8-1.PNG?raw=true)


<br>
<br>
<br>

## 문제 3번

## 3. 디지털 시계 만들기

[코드]
```js
<!DOCTYPE html>
<html lang="ko">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>현재 날짜와 시각은?</title>
  <link rel="stylesheet" href="css/today.css">
</head>
<body>
  <div id="container">
    <div id="today">
      <!-- 현재 날짜 -->
    </div>
    <div id="clock">
      <!-- 현재 시간 -->
    </div>
  </div>
<script>
    function display() {

      const today = new Date(); //현재 날짜
      const displayDate = document.querySelector("#today");
      const displayTime = document.querySelector("#clock");

      let day = ""; //요일
      switch(today.getDay()){
        case 0:
          day = "일";break;
        case 1:
          day = "월";break;
        case 2:
          day = "화";break;
        case 3:
          day = "수";break;
        case 4:
          day = "목";break;
        case 5:
          day = "금";break;
        case 6:
          day = "토";break;

      }
    
      let text = `${today.getFullYear()}년 ${today.getMonth()+1}월 ${today.getDate()}일 ${day}요일`;
      displayDate.innerHTML = text; //날짜 찍기

      let h = today.getHours(); //시간
      const ampm = (h < 12) ? "AM" : "PM";
      h = (h > 12) ? h -12 : h; //13시 이후 처리 
      h = (h == 0)? 12 : h; //시간이 두자리 수, 한자리 수처리

      const hStr = (h < 10 ) ? "0"+h: ""+h;
      let min = today.getMinutes();
      const minstr = (min < 10)? "0"+min : ""+min;
      let sec = today.getSeconds();
      const secstr = (sec < 10)? "0"+sec : ""+sec;

      text = `${ampm} ${hStr}시 ${minstr} 분 ${secstr} 초`;
      displayTime.innerHTML = text;
    }

    setInterval(display,1000);
    
   
  </script>
</body>
</html>
```
<br>
## [스크립트 부분]
<br>

```js
<script>
    function display() {

      const today = new Date(); //현재 날짜
      const displayDate = document.querySelector("#today");
      const displayTime = document.querySelector("#clock");

      let day = ""; //요일
      switch(today.getDay()){
        case 0:
          day = "일";break;
        case 1:
          day = "월";break;
        case 2:
          day = "화";break;
        case 3:
          day = "수";break;
        case 4:
          day = "목";break;
        case 5:
          day = "금";break;
        case 6:
          day = "토";break;

      }
    
      let text = `${today.getFullYear()}년 ${today.getMonth()+1}월 ${today.getDate()}일 ${day}요일`;
      displayDate.innerHTML = text; //날짜 찍기

      let h = today.getHours(); //시간
      const ampm = (h < 12) ? "AM" : "PM";
      h = (h > 12) ? h -12 : h; //13시 이후 처리 
      h = (h == 0)? 12 : h; //시간이 두자리 수, 한자리 수처리

      const hStr = (h < 10 ) ? "0"+h: ""+h;
      let min = today.getMinutes();
      const minstr = (min < 10)? "0"+min : ""+min;
      let sec = today.getSeconds();
      const secstr = (sec < 10)? "0"+sec : ""+sec;

      text = `${ampm} ${hStr}시 ${minstr} 분 ${secstr} 초`;
      displayTime.innerHTML = text;
    }

    setInterval(display,1000);
    
   
  </script>
```
![test1](https://github.com/leejieun9/leejieun9.github.io/blob/master/docs/assets/images/8-4.PNG?raw=true) <br>

## 4번

## 4. 08\js\circle.js에서 결괏값을 반올림하는 소스로 수정해 보세요.

[코드]
```js
function area(r) {
  return Math.PI * r * r;
}
function circum(r) {
  return 2 * Math.PI * r;
}

const result = document.querySelector("#result"); // 결괏값을 표시할 부분
const radius = prompt("반지름의 크기는? ");

// 반올림하지 않았을 때
// result.innerText = `
//     반지름 : ${radius},
//     원의 넓이 : ${area(radius)},
//     원의 둘레 : ${circum(radius)}
//   `;

// 반올림
result.innerText = `
    반지름 : ${radius},
    원의 넓이 : ${Math.round(area(radius))},
    원의 둘레 : ${Math.round(circum(radius).toFixed(3))}
  `;

```

![test1](https://github.com/leejieun9/leejieun9.github.io/blob/master/docs/assets/images/8-3.PNG?raw=true) <br>


![test1](https://github.com/leejieun9/leejieun9.github.io/blob/master/docs/assets/images/8-2.PNG?raw=true) <br>

## 문제 5번

### 5. 웹 문서의 배경 이미지 무작위로 변경하기

[코드]

```js
 <script>
    const h1 = document.querySelector("h1");
    const body = document.querySelector("body");

    h1.addEventListener("click", function(){
      const sel = Math.floor(Math.random()*5 +1);
      body.style.backgroundImage = `url('images/bg-${sel}.jpg')`;  
    });
</script>

```

## 문제 6번

## 6. 생년월일을 입력하고 [계산] 버튼을 클릭하면 생일로부터 지금까지 며칠이 지났는지, 또는 몇 시간이 지났는지 보여주는 프로그램을 작성하세요.

[코드]
```js


```
​

[결과]

​

​## 문제 7번


### 7. 무작위로 이벤트 당첨자를 뽑는 프로그램을 만들려고 한다. 전체 몇 명인지, 그리고 그 중에서 몇 명을 뽑을 것인지 입력한 후 [추첨] 버튼을 클릭하면 해당 숫자만큼 당첨자를 뽑아서 화면에 표시하는 프로그램을 작성하시오.

[코드]
```js
const raffle = document.querySelector("#raffle");

raffle.addEventListener("click", (e) => {
  e.preventDefault();  
  const seed = document.querySelector("#seed");
  const total = document.querySelector("#total");
  const result = document.querySelector("#result");
  let  winner = "";

  for(let i = 0; i < total.value; i++) {
    let picked = Math.floor((Math.random() * seed.value) + 1);
    winner += `${picked}번, `;      
  }  
  
  result.innerText = `당첨자 : ${winner}`;
  result.classList.add("show");
});
```

[결과]

![test1](https://github.com/leejieun9/leejieun9.github.io/blob/master/docs/assets/images/8-5.PNG?raw=true) <br>
