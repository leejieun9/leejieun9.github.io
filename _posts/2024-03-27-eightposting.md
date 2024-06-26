---
categories: JavaScripts
title: "자바스크립트 5장 DOM 기초 과제"
date: 2024-03-30 00:23:03
toc: true
---

짧게 말해봅니다. 
<br>
<br>
이무진이 부릅니다 -과제곡-

 ~~알아서 머리속 재생하시면서 보십쇼~~
<br>
<br>
---

## 문제1번

## 1. 다음 코드에서 p 요소 노드를 선택하는 방법으로 올바르지 않은 것을 고르세요.

<body>
  <div class="box1">
  <p id="text">Select Text</p>
  </div>
  </body>

<span style="color:red"> ① document.getElementById("#text")<br> </span> 

② document.querySelector("p")<br>

③ document.querySelector(".box1 > p")<br>

④ document.querySelectorAll("p")[0]<br>

해설: 정답은? 1번<br>

1번의 document.getElementBtld() 는 id 속성 이기 때문에 #이 아니다.
 <br>

<br>
<br>

## 문제 2번
<br>

## 2. 다음과 같은 코드에서 sample text를 클릭했을 때, p 태그의 fz20 클래스 속성을 삭제하고, sample text를 change text로 변경하고 싶다면 (가), (나)에 들어갈 내용으로 맞게 짝지어진 것을 고르세요.

<br>

```js
    <p id="text" class="red-color fz20">sample text</p>
    <script>
        const pEl = document.querySelector("#text");
        pEl.onclick = () => {
            pEl.(가) = "change text"; 
            pEl.(나);
        }
    </script>
 ```
<br>
  (가) - (나)

① dataset - removeClass("fz20") <br>

② dataset - setAttribute("fz20") <br>

③ innerHTML - toggleClass() <br>

<span style="color:red"> ④ innerText - classList.remove("fz20") </span> <br>

⑤ textContent - removeClass("fz20") <br>

  정답은? : 4번 <br>
  // 요소.classList.remove(클래스명)

<br>
<br>


## 문제 3번

## 3. 자바스크립트 코드를 작성하여 리스트를 클릭했을 때 리스트의 배경색을 yellowgreen으로 변경하시오.

힌트)

> *ol 태그를 선택한다.*
<br>
>*ol 태그를 클릭했을 때 배경색을 yellowgreen으로 설정한다.*
 <br>

```js
<!DOCTYPE html>
<html lang="ko">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width", initial-scale="1.0">
    <title>라면 끓이기</title>
</head>
<body>
    <h1>라면을 끓이는 순서</h1>
    <ol type="A">
        <li>물을 끓인다.</li>
        <li>라면과 스프를 넣는다.</li>
        <li>파를 썰어 넣는다.</li>
        <li>5분 후 <strong>맛있게</strong> 먹는다.</li>
    </ol>
    <script>
    // 이곳에 코드를 작성하세요.

        const ol = document.querySelector("ol");

        ol.onclick = () => {
          ol.style.backgroundColor= "yellowgreen";
        };

    </script>
</body>
</html>
```
<br>
<br>
<br>

  
## 문제4번

## 4. 다음 코드의 입력 항목 중 나이 항목의 값을 가져오는 코드를 고르세요.
<br>
<form name="frm1">
  <label for="uname">이름</label>
  <input type="text" id="uname" name="uname">
  <label for="age">나이</label>
  <input type="text" id="age" name="age">
  <button type="submit">전송</button>
</form>
<br>

<span style="color:red"> ① document.frm1.age.value </span> <br>

② document.forms.age.value<br>

③ document.forms[0].uname.value <br>

④ document.frm1.elements[0].value <br>

⑤ document.forms[0].elements[0].value <br>

해설: 정답은? 1번

 <br>

## 문제5번

## 5. 아래 힌트를 참고해 항목 앞에 있는 체크 표시를 누르면 항목 텍스트의 글자가 회색(#ccc)으로 바뀌면서 가로줄이 그려지도록 자바스크립트 코드를 작성하시오.

![test1](https://github.com/leejieun9/leejieun9.github.io/blob/master/docs/assets/images/5-1.png?raw=true)
  
  ```js
<!DOCTYPE html>
<html lang="ko">
<head>
	<meta charset="UTF-8">
	<meta name="viewport" content="width=device-width, initial-scale=1.0">
	<title>연습문제 1</title>
	<style>
		ul{
			list-style: none;
		}
		li {
			font-size:20px; 
			line-height: 35px;
		}
		.check {			
			color:#ccc;
			font-size:20px;
			margin-right:25px;
		}
		.check:hover {
			color:#222;
		}
	</style>
</head>
<body>
	<h1>할 일 목록</h1>
	<ul>
		<li><span class="check">&check;</span>할 일 1 </li>
		<li><span class="check">&check;</span>할 일 2 </li>
		<li><span class="check">&check;</span>할 일 3 </li>
		<li><span class="check">&check;</span>할 일 4 </li>
		<li><span class="check">&check;</span>할 일 5 </li>
	</ul>
    <script>

        /* 이곳에 작성하시오 */

document.querySelectorAll(".check");
const check = document.querySelectorAll(".check");

for(let i=0;i<check.length;i++){

  
    check[i].onclick = function() {
      check[i].parentNode.style.color = "#ccc";
      check[i].parentNode.style.textDecoration = "line-through";
    }
    
}

var mother = check.parentNode;

	</script>
</body>
</html>

```

*힌트:

* 1) 체크 표시 부분을 가져와 노드리스트를 만든다. 여기에서는 <span class="check"> 요소를 이용한다.* <br>

* 2) for나 forEach 문을 이용해 노드 리스트에 있는 요소 전체를 반복하면서 click 이벤트가 발생하면 실행할 함수를 연결한다.*<br>

* 3) 클릭이 발생한 요소에서 글자 색상 스타일(color)을 회색(#ccc)으로 바꾼다. 체크 표시와 텍스트의 색상도 바뀌므로 클릭이 발생한 요소의 부모 노드에서 작업해야 한다. 해당 요소의 부모노드에 접근하려면 요소 이름 뒤에 .parentNode라고 붙이면 된다. 즉, 요소.parentNode 라 하면 된다.*<br>

* 4) 클릭한 요소의 부모 노드에서 밑줄 스타일(text-decoration)을 가로줄(line-through)로 바꾼다.  여기에서도 체크 표시와 텍스트도 가로줄을 그어야 한다는 점에 주의한다*
<br>
<br>
