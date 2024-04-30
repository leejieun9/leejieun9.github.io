---
categories: JavaScripts
title: " 자바스크립트 11장 배열과 객체 더 깊게 살펴보기 과제"
date: 2024-04-30 07:00:025
toc : true
---

도시 이름이 들어 있는 배열 cities는 다음과 같다.

```js
let cities = ["서울", "베를린", "리오데자네이루", "코펜하겐", "로스엔젤레스"];
```

<br>
다음 문항에서 요구하는 자바스크립트 코드를 작성하되, for 문과 같은 반복문을 사용하지 말고 작성해 보시오.
<br>

1> cities 배열에 들어 있는 도시 이름들을 출력하시오.<br>

2> cities 배열에 서 가장 긴 도시 이름을 출력하시오.<br>

3> cities 배열에서 가나다 순으로 가장 먼저 나오는 도시 이름을 출력하시오.<br>

​

[실행 결과]

![test1](https://github.com/leejieun9/leejieun9.github.io/blob/master/docs/assets/images/10-5.PNG?raw=true)

[코드]

```js
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=<device-width>, initial-scale=1.0">
    <title>Document</title>
    <style>
        container{
            width:600px;
            margin:20px auto;
        }
        h1 {
            font-size:1.5em;
        }
        li {
            font-size:1rem;
            line-height: 2;
        }
    </style>
</head>
<body>
    <div id="container">
        <h1>문자열 배열 다루기</h1>
        <ul id="result">
        </ul>
    </div>
    <script>
        // 이 곳에 작성하세요
      let cities = ["서울", "베를린", "리오데자네이루", "코펜하겐", "로스엔젤레스"];
      let citiesStr = cities.join(" ");
        document.getElementById("result").innerHTML += "<li>1> " + citiesStr + "</li>";

    let longestCity = cities.reduce((a, b) => {
            if (a.length < b.length) {
                return b;
            } else {
                return a;
            }
        }, cities[0]);
        document.getElementById("result").innerHTML += "<li>2> " + longestCity + "</li>";

        let sortedCities = cities.sort();
        document.getElementById("result").innerHTML += "<li>3> " + sortedCities[0] + "</li>";
    </script>

</body>
</html>
```

![test1](https://github.com/leejieun9/leejieun9.github.io/blob/master/docs/assets/images/10-6.PNG?raw=true)
