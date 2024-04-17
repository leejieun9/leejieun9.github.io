---
categories: JavaScripts
title: "자바스크립트 7장 DOM 활용하기 실습 보고서(2) "
date: 2024-04-16 00:23:03
toc: true
---

## 문제1번

### 1. 부할 주제를 입력하고 추가 버튼을 누르면 화면에 입력값이 계속 추가되어 나타나고, 입력값을 클릭하면 없어지도록 만들어 보시오. <br>

<br>
<br>

힌트 <br>

  *button 요소의 onclick 속성에 newRegister()라는 자바스크립트 함수가 할당되어 있으므로,* <br>
 *script 부분에 newRegister()라는 함수를 작성한다.* <br>
 *input 요소에 입력된 값을 가져온다.* <br>
 *출력할 요소로 itemList를 선택한다.* <br>
 *ul 요소안에 놓일 요소이므로 li 노드를 생한다.*<br>
 *li 노드의 텍스트로  input 요소에 입력된 값을 할당한다.* <br>
 *li 노드의 onclick 속성에 또는 이벤트 리스너를 만들어 자기자신을 삭제하는 코드를 할당한다.* <br>
   *자기자신을 삭제하는 코드는 자신의 부모를 찾아 자식으로서 자신을 삭제하는 것으로 익명함수로 처리한다.* <br>
 *itemList의 자식 노드로 li 요소를 연결한다.* <br>
 *다음 사용을 위해 input 요소에 입력된 값은 지운다.* <br>

<br>
	 

<br>

**[코드]** <br>

```js
 <script>
    function newRegister(){
        const subject = document.querySelector("#subject").value;
        const itemList = document.querySelector("#itemList");

        const liNode = document.createElement("li");
     // liNodeText = document.createTextNode(subject.innerText);

        liNode.textContent = subject;

        liNode.addEventListener("click", function(e){
            e.preventDefault();
            this.parentNode.removeChile(this);
        });

        itemList.appendChild(liNode);
        document.querySelector("#subjet").value="";


    }
  </script>
```
<br>


[결과창] <br> 
![test1](https://github.com/leejieun9/leejieun9.github.io/blob/master/docs/assets/images/7-8.PNG?raw=true)
<br>

## 문제2번

### 2.행(row)과 열(column)의 개수를 입력한 값에 따라 힌트를 참고하여 표를 그리는 소스를 작성하세요.** <br>
**표를 구성하는 table, td, tr 요소의 관계를 잘 생각하고 노드를 추가하여 작성하세요.** <br>
**여기에서는 작성한 소스가 완벽하지 않더라도 DOM을 사용해 표를 그리는 것에 집중해 만들어 보세요.** <br>

*힌트*

1) table 요소 노드를 만듭니다.<br>

2) 입력한 행의 개수만큼 반복하면서 tr 요소노드를 만듭니다.<br>

3) 입력한 열의 개수만큼 다음 과정을 반복합니다.<br>

    (1) td 요소노드를 만듭니다.<br>

    (2) 텍스트 노드를 만듭니다.<br>

    (3) 텍스트 노드를 td 요소 노드의 자식 노드로 만듭니다. <br>

    (4) td 요소를 tr 노드의 자식 노드로 만듭니다. <br>
<br>

4) tr 요소 노드를 table 요소 노드의 자식 노드로 만듭니다.
<br>
5) table 요소 노드를 필요한 위치에 추가합니다.

<br>
<br>
<br>


<br>

**[코드]** <br>

```js
<!DOCTYPE html>
<html lang="ko">
<head>
	<meta charset="UTF-8">
	<meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>과제 2</title>
  <style>
    form {
      margin-bottom:30px;
    }
    input[type="text"] {
      width:30px;
      height:20px;
      text-align: center;
    }
    button {
      margin-left:10px;
    }
    table {
      width:300px;      
    }
    table, td {
      border:1px solid #ccc;
      border-collapse: collapse;
    }
    td {
      padding:10px;
    }
  </style>
</head>
<body>
  <form>
    <input type="text" id="rCount" value="1">행 
    <input type="text" id="cCount" value="1">열    
    <button id="bttn">작성</button>
  </form>
  <div id="contents"></div>

    // 이곳에 작성하세요.
    <script>
let bttn = document.querySelector("#bttn");
bttn.addEventListener("click", function (event) {
    event.preventDefault(); // 기본 이벤트 방지
    let table = document.createElement("table");

    // 입력한 행 개수만큼 반복
    for (let i = 0; i < rCount.value; i++) {
        // tr 요소노드 만들기
        let tr = document.createElement("tr");
    

         // 입력한 열 개수만큼 반복
         for (let j = 0; j < cCount.value; j++) {
                // td 요소노드 만들기
                let td = document.createElement("td");
                // 텍스트 요소노드 
                let text = document.createTextNode("가나다");
                // 텍스트 노드를 td 자식으로 추가
                td.appendChild(text);
                // td 행의 자식으로 추가
                tr.appendChild(td);
            }

            // tr 요소 노드를 table 요소 노드의 자식 노드
            table.appendChild(tr);

        var contents = document.querySelector("#contents");
        contents.innerHTML = ""; // contents 요소 초기화
        contents.appendChild(table);
        }        
    });

  </script>
</body>
</html>

```
<br>

**[결과창]** <br>

![test1](https://github.com/leejieun9/leejieun9.github.io/blob/master/docs/assets/images/7-9.PNG?raw=true)
<br>
<br>
