---
categories: Stringboot
title: "4장 롬복과 리팩터링"
date: 2024-05-22 00:23:03
toc: true
---
뭔가 어려운데 알것같으면서도 어렵고 어렵다...어렵다아ㅏ아ㅏ!!!
<br>
<br>
<br>
---


1분 퀴즈

​
1. 다음 ㉠~㉤에 들어갈 알맞은 용어를 찾아 쓰세요. <br>
<br>
​<br>

(  ㉠  ): 롬복을 설치하기 위해 값 변경이 필요한 파일 <br>

(  ㉡  ): 모든 필드를 매개변수로 하는 생성자를 만드는 롬복 어노테이션 <br>

(  ㉢  ): toString() 메서드를 대체하는 롬복 어노테이션 <br>

(  ㉣  ): 로깅 기능을 사용하기 위해 필요한 롬복 어노테이션 <br>

(  ㉤  ): 출력하기 원하는 데이터를 로그로 찍기 위해 사용하는 구문 <br>

​
<br>
① @AllArgsConstructor <br>

② build.gradle <br>

③ @Slf4j <br>

④ @ToString <br>

⑤ log.info() <br>

답:

㉠ build.gradle <br>
㉡ @AllArgsConstructor <br>
㉢ @ToString <br>
㉣ @Slf4j <br>
㉤ log.info() <br>
​

​

셀프 퀴즈 <br>
<br>
​<br>

3장 셀프체크에서 만든 다음 코드를 롬복으로 리팩터링하기 <br>

```js
- dto/MemberForm.java

[코드]

 package com.example.firstproject.dto;

import com.example.firstproject.entity.Article;
import com.example.firstproject.entity.Member;
import lombok.AllArgsConstructor;
import lombok.ToString;

@AllArgsConstructor
@ToString
public class MemberForm {
    private String email;
    private String password;


    public Member toEntity() {
        return new Member(null,email,password);
    }
}


​
```
<br>
<br>

```js

// controller/MemberController.java
package com.example.firstproject.controller;

import com.example.firstproject.dto.MemberForm;
import com.example.firstproject.entity.Member;
import com.example.firstproject.repository.MemberRepository;
import lombok.extern.slf4j.Slf4j;
import org.slf4j.Logger;
import org.slf4j.LoggerFactory;
import org.springframework.beans.factory.annotation.Autowired;
import org.springframework.stereotype.Controller;
import org.springframework.ui.Model;
import org.springframework.web.bind.annotation.GetMapping;
import org.springframework.web.bind.annotation.PathVariable;
import org.springframework.web.bind.annotation.PostMapping;

import java.util.List;

@Slf4j
@Controller
public class MemberController {
    private static final Logger log = LoggerFactory.getLogger(MemberController.class);
    @Autowired
    private MemberRepository memberRepository;

    @GetMapping("/signup")
    public String newMemberForm() {
        return "members/new";
    }

    @PostMapping("/join")
    public String createMember(MemberForm form) {
        log.info(form.toString());
//        System.out.println(form.toString());
        //1.DTO를 엔티티로 변환
        Member member = form.toEntity();
        log.info(member.toString());
        //System.out.println(member.toString());

        //2. 리파지터리로 엔티티를 DB에 저장
        Member saved = memberRepository.save(member);
        log.info(saved.toString());
        //System.out.println(saved.toString());
        return "";
    }

    @GetMapping("/members/{id}")
    public String show(@PathVariable Long id, Model model) {

        Member memberEntity = memberRepository.findById(id).orElse(null);

        model.addAttribute("member", memberEntity);
        return "members/show1";
    }

    @GetMapping("/members")
    public String index(Model model) {
        List<Member> memberEntityList = (List<Member>) memberRepository.findAll();

        model.addAttribute("memberList", memberEntityList);
        return "members/index1";
    }

}

```
<br>
<br>

```js
//show1.mustache

{{>layouts/header}}

<table class="table">
    <thead>
    <tr>
        <th scope="col">Id</th>
        <th scope="col">email</th>
        <th scope="col">password</th>
    </tr>
    </thead>
    <tbody>
    {{#member}}
        <tr>
            <th scope="row">{{id}}</th>
            <td>{{email}}</td>
            <td>{{password}}</td>
        </tr>
    {{/member}}
    </tbody>
</table>

{{>layouts/footer}}
```
<br>
<br>

```js

//file: index.mustache

{{>layouts/header}}

<table class="table">
    <thead>
    <tr>
        <th scope="col">Id</th>
        <th scope="col">email</th>
        <th scope="col">password</th>
    </tr>
    </thead>
    <tbody>
    {{#memberList}}
        <tr>
            <th scope="row">{{id}}</th>
            <td>{{email}}</td>
            <td>{{password}}</td>
        </tr>
    {{/memberList}}
    </tbody>
</table>


{{>layouts/footer}}

```
<br>
<br>

​![test](https://github.com/leejieun9/leejieun9.github.io/blob/master/docs/assets/images/stringboot4-1.png?raw=true)
![test](https://github.com/leejieun9/leejieun9.github.io/blob/master/docs/assets/images/stringboot4-2.png?raw=true)
![test](https://github.com/leejieun9/leejieun9.github.io/blob/master/docs/assets/images/stringboot4-3.png?raw=true)

[코드]
[출처] 4장 실습|작성자 AI소프트웨어과
