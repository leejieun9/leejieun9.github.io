---
categories: JavaScripts
title: " 13장 비동기 프로그래밍 실습 보고서"
date: 2024-04-30 12:00:03
toc : true
---

## 1. 다음 사이트에는 영문으로 된 명언이 JSON 형식으로 저장되어 있습니다.

// dummyjson.com/quotes

> 위 사이트에서 JSON 데이터를 가져온 후 콘솔창에 결과를 표시해 보세요.

​

사용할 파일

13\quiz-1.html  

​

힌트

> fetch와 then, catch를 사용해서 URL에서 자료를 가져온다.

> 가져온 데이터에 어떤 값이 어떤 구조로 되어 있는 지 확인하고, 그 중에서 명언과 말한 사람 정보를 가져오는 방법을 생각한다.

<br>


```js
[코드]

  <script>
    fetch("https://dummyjson.com/quotes")
    .then(response => response.json())
    .then(qutoes => console.log(qutoes));
  </script>

```


<br>
​<br>

## 2. 마무리 문제1에서 명언 데이터를 가져오는 데 성공했으면 그 중에서 1개의 명언만 가져와서 문서의 #result 영역에 명언 내용과 말한 사람을 표시해 보세요. 이때 명언 내용은 #result 영역에 있는 .quote 영역에, 말한 사람은 .author 영역에 표시하세요.

​

>사용할 파일

>12\quiz-2.html  



힌트

- 마무리 문제1에서 한 번에 몇 개의 명언을 가져오는 지 확인했으면 1과 그 숫자 사이의 무작위 값을 추출한다.

- 무작위 수를 사용해서 명언을 가져온 후 명언 부분과 말한 사람 이름을 나눠서 화면 영역에 표시한다.

​
```js

[코드]

​<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Random Quotes</title>
  <link rel="stylesheet" href="css/quotes.css">
</head>
<body>
  <div id="result">
    <div class="quote"></div> 
    <div class="author"></div>
  </div>
</body>

<script>
  fetch("https://dummyjson.com/quotes")
  .then(response => response.json())
  .then(qutoes => {
    const idx = Math.floor(Math.random()*30);
    const quote = qutoes.quotes[idx];

  console.log(quote)
  document.querySelector(".quote").innerHTML = quote.quote;
  document.querySelector(".author").innerHTML = quote.author;
  });
  
</script>

</html>

```

[결과]

​![test1](https://github.com/leejieun9/leejieun9.github.io/blob/master/docs/assets/images/13-1.PNG.PNG?raw=true)
