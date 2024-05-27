---
categories: Stringboot
title: "2장 MVC 패턴이해와 실습 (과제)"
date: 2024-05-27 00:23:03
toc: true
---

## 스프링부트 2장 과제(1)

 this list will be replaced by the table of contents
{:toc .large-only}
  <br> 
  <br>
  <br>
  <br>

## 문제 1번

<br>

### 1. 새로 고칠 때마다 랜덤으로 이미지가 나오는 페이지를 만들려고 한다.

<br>
<br>

스프링부트의 resources/static 폴더에 images 폴더를 생성하고, 첨부된 images.zip 파일을 내려받아서 압축을 푼다.
<br>

* 접근 경로: localhost:8080/random-image <br>

* 컨트롤러: SecondController 에 메서드 추가 <br>
* 뷰 템플릿 파일: image.mustache (신규 작성)

<br>
<br>
<br>
<br>

## 답
<br>
```js
//file: SecondController.java

package com.example.demo.controller;

import org.springframework.stereotype.Controller;
import org.springframework.ui.Model;
import org.springframework.web.bind.annotation.GetMapping;

import java.nio.file.Path;
import java.nio.file.Paths;

@Controller
public class ImgeController {
    @GetMapping("/random-image")

    public String randomImages(Model model){
        String[] images = {

                "images/pic-1.jpg",
                "images/pic-2.jpg",
                "images/pic-3.jpg",
                "images/pic-4.jpg",
                "images/pic-5.jpg",
                "images/pic-6.jpg"
        };
        int randInt = (int) (Math.random() * 6);
        model.addAttribute("randomImages",images[randInt]);
        return "image";
    }
}
```

<br>
<br>

```js
//file: image.mustache

{{>layouts/header}}

<div class = "bg-dark text-white p-5">
    <img src={{randomImages}}>
</div>

{{>layouts/footer}}
```
<br>
<br>
<br>
