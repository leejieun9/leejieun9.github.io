---
categories: Stringboot
title: "게시판만들고 새글 작성하기"
date: 2024-05-14 00:23:03
toc: true
---

<br>
<br>
<br>
---

## 문제1번

### 1. 다음 중 옳지 않은 것을 고르세요. <br>
<br>
① <form> 태그의 action 속성에는 데이터를 전달할 URL 주소가 담긴다. <br>
② <form> 태그의 method 속성에는 get만 사용할 수 있다. <br>
③ @PostMapping 어노테이션은 post 방식으로 전달된 요청을 받아 컨트롤러의 메서드에 전달한다. <br>
④ 폼 데이터를 자동으로 받으려면 입력 폼에서 input , <textarea> 태그의 name 속성과 DTO 클래스의 필드명이 같아야 한다.
 <br>

<br>
2번 
모르겠고 실습할때  get을 쓴적이 없음
<br>


## 2번

### 2. 다음 ㉠~㉢에 들어갈 용어를 쓰세요.

( ㉠ )(이)란 JPA에서 제공하는 어노테이션으로, 이를 부여받은 클래스를 기반으로 DB 속 테이블이 생성됩니다. <br>
( ㉡ )(이)란 JPA에서 제공하는 인터페이스로, 이를 상속해 엔티티를 관리(생성, 조회, 수정, 삭제)할 수 있습니다. 해당 인터페이스는 2개의 제네릭 요소를 받습니다. 하나는 관리할 대상 엔티티의 클래스 타입이고, 또 다른 하나는 그 엔티티의 대푯값 타입입니다. <br>
( ㉢ )은/는 스프링 부트에서 제공하는 어노테이션으로, 이를 컨트롤러의 필드에 부여할 수 있습니다. 해당 어노테이션은 스프링 부트가 만들어 놓은 객체를 가져와 주입해 줍니다. <br>


> ㄱ-Entity <br>
> ㄴ-Repository <br>
> ㄷ- Autowired <br>





## 3번
### 3. 다음 ㉠~㉤에 들어갈 알맞은 용어를 찾아 쓰세요.

(  ㉠  ): DB에서 데이터를 저장하는 틀 <br>
(  ㉡  ): 테이블의 행(row)을 표현하는 또 다른 말 <br>
(  ㉢  ): 데이터의 생성/조회/수정/삭제를 뜻하는 말 <br>
(  ㉣  ): 테이블에 데이터를 생성하는 SQL 문 <br>
(  ㉤  ): 테이블에 데이터를 조회하는 SQL 문 <br>

① INSERT <br>
② 테이블 <br>
③ SELECT <br>
④ CRUD <br>
⑤ 레코드 <br>

> ㄱ - 테이블 <br>
> ㄴ - 레코드 <br>
> ㄷ - CRUD <br> 
> ㄹ - INSERT <br>
> ㅁ - SELECT <br>



 ## SELF CHECK
###  <회원 가입 페이지> 코드가 다음과 같을 때 컨트롤러, DTO, 엔티티, 리파지터리 구현하기 <br>

1. 컨트롤러: controller/MemberController.java <br>

```js
package com.example.firstproject.controller;

import com.example.firstproject.dto.MemberForm;
import com.example.firstproject.entity.Member;
import com.example.firstproject.repository.MemberRepository;
import org.springframework.beans.factory.annotation.Autowired;
import org.springframework.stereotype.Controller;
import org.springframework.web.bind.annotation.GetMapping;
import org.springframework.web.bind.annotation.PostMapping;

@Controller
public class MemberController {
    @Autowired
    private MemberRepository memberRepository;
    @GetMapping("/signup")
    public String newMemberForm(){
        return "members/new";
    }


    @PostMapping("/join")
    public String createMember(MemberForm form){
        System.out.println(form.toString());
        Member member= form.toEntity();
        System.out.println(member.toString());
        Member saved = memberRepository.save(member);
        System.out.println(saved.toString());
        return"";
    }
}

```
2. DTO: dto/MemberForm.java
```js
package com.example.firstproject.dto;

import com.example.firstproject.entity.Member;

public class MemberForm{
    private String email;
    private String password;

    public MemberForm(String email, String password) {
        this.email = email;
        this.password = password;
    }

    @Override
    public String toString() {
        return "MemberForm{" +
                "email='" + email + '\'' +
                ", password='" + password + '\'' +
                '}';
    }

    public Member toEntity() {
        return new Member (null,email,password);
    }
}
```

<br>
<br>
<br>

3. 엔티티: entity/Member.java <br>
<br>
<br>
```js
package com.example.firstproject.entity;

import jakarta.persistence.Column;
import jakarta.persistence.Entity;
import jakarta.persistence.GeneratedValue;
import jakarta.persistence.Id;

@Entity
public class Member {

    @Id
    @GeneratedValue
    private Long id;
    @Column
    private String email;

    @Column
    private String password;
    public Member(Long id, String email, String password) {
        this.id = id;
        this.email = email;
        this.password = password;
    }

    @Override
    public String toString() {
        return "Member{" +
                "id=" + id +
                ", title='" + email + '\'' +
                ", content='" + password + '\'' +
                '}';
    }
}

```
<br>
<br>
<br>

4. 리파지터리: repository/MemberRepository.java <br>

<br>
<br>

```js
package com.example.firstproject.repository;

import com.example.firstproject.entity.Member;
import org.springframework.data.repository.CrudRepository;

public interface MemberRepository extends CrudRepository<Member,Long> {
}

```
<br>
<br>

