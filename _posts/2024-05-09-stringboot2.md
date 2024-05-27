---
categories: Stringboot
title: "2장 MVC 패턴이해와 실습"
date: 2024-05-09 00:23:03
toc: true
---
<br>
<br>
---

## 문제1번

### 1. 다음 ㉠~㉤에 들어갈 알맞은 용어를 찾아 쓰세요.

( ㉠ )(이)란 웹 페이지를 일종의 틀로 만든 것이다. <br>
( ㉡ )은/는 클라이언트의 요청을 받아 서버에서 이를 처리하는 역할을 한다.<br>
( ㉢ )은/는 뷰 템플릿에서 사용되는 데이터를 관리하는 역할을 한다.<br>
( ㉣ )은/는 이 클래스가 컨트롤러임을 선언한다.<br>
( ㉤ )은/는 클라이언트의 URL 요청을 받아 특정 컨트롤러의 메서드가 처리하게 한다.<br>

① @Controller
② 컨트롤러
③ @GetMapping
④ 뷰 템플릿
⑤ 모델

> ㄱ-4 <뷰 템플릿>
> ㄴ-2 <컨트롤러>
> ㄷ-5 <모델>
> ㄹ-1 <@Controller>
> ㅁ-3 <@GetMapping>

<br>
<br>


## 2번

### 2. 다음 설명 중 옳지 않은 것을 고르세요.

① 웹 브라우저는 서버로 URL 요청을 보내 결과 뷰 템플릿 페이지를 반환받는다. <br>
② 컨트롤러의 메서드는 URL 요청을 받아 처리한 후 결과 뷰 템플릿 페이지를 반환한다.<br>
③ 컨트롤러의 메서드 반환값은 뷰 템플릿 페이지의 확장자를 포함해 작성한다.<br>
④ 뷰 템플릿 페이지에서 변수를 사용하려면 모델에 변수가 등록돼 있어야 한다.<br>

> 3번 <br>

[해설]- 확장자를 빼야한다



## 3번
### 3. 다음 ㉠~㉢에 들어갈 알맞은 용어를 쓰세요.

(  ㉠  )(이)란 화면에 요소를 배치하는 것을 말한다. 웹 페이지는 같은 요소로도 어떻게 배치하느냐에 따라 다른 느낌을 줄 수 있다. <br>
(  ㉡  )(이)란 웹 페이지를 쉽게 만들 수 있도록 작성해 놓은 코드 모음으로 미리 작성된 HTML/CSS/자바스크립트 코드를 가져다 사용할 수 있다.<br>
(  ㉢  )(이)란 코드를 하나의 틀로 만들어 변수화하는 것을 말한다.<br>

​ㄱ-레이아웃 <br>
ㄴ-부트스트랩 <br>
ㄷ-탬플릿화 <br>

!selfcheak!

```js
// SecondController class
package com.example.firstproject.controller;

import org.springframework.stereotype.Controller;
import org.springframework.ui.Model;
import org.springframework.web.bind.annotation.GetMapping;

    @Controller
    public class SecondController {

        @GetMapping("/random-quote")
        public String niceToMeetYou(Model model){
            String[] quotes = {
                    "행복은 습관이다.그것을 몸에 지니라." +"-하버드-",
                    "최저에 맞추지말고 최선을 다해 최대에 맞춰라" + "-익명-",
                    "집에 도착하면 쉬는게 도리이다.",
                    "세상은 누구나 미워한다. 자격지심 갖지말아라" + "-익명-",
                    "당신이 할 수 있다고 믿든 할 수 없다고 믿든 믿는대로 될 것이다."};

      int randInt = (int)(Math.random() * quotes.length);
        model.addAttribute("randomQuote",quotes[randInt]);
        return "quote";



    }
}
```
```js
//quote.mustache

{{>layouts/header}}
    <div class = "bg-dark text-white p-5">
        <h1>{{randomQuote}}</h1>
    </div>
{{>layouts/footer}}
```

[결과화면]
![test](https://github.com/leejieun9/leejieun9.github.io/blob/master/docs/assets/images/stringboot2-1.PNG?raw=true)
​
