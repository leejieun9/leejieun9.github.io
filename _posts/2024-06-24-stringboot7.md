---
categories: Stringboot
title: " 7장 실습"
date: 2024-06-24 00:23:03
toc : true
---

## 스프링부트 7장 실습(1)
  <br> 
  <br>
  <br>
  <br>

## 문제 1번

### 1. 페이지가 나올 때까지 처리 흐름을 순서대로 작성하세요.

<br>
<br>

① 클라이언트로부터 데이터 수정 요청이 들어온다. <br>
② 뷰 페이지에 수정할 데이터를 함께 보여 준다. <br>
③ 수정 요청 데이터를 DB에서 찾는다. <br>
④ 수정 요청 데이터를 모델에 등록한다.
<br>
​<br>
<br>
<br>

**답**
<br>
1 -> 3 -> 4 -> 2
<br>
<br>

## 문제 2번

### 셀프체크에서 만든 <회원가입 페이지>에서 [Submit] 버튼을 클릭하면 <상세 페이지>로 이동하고
<br>

|     데이터 관리     |     SQL     |    HTTP       
|:--------------------|:-----------|:----------
|  데이터 생성(Create) |   INSERT   |    ㉠        
|         ㉡          |   SELECT   |    GET       
| 데이터 수정(Update)  |     ㉢     |    PATCH(PUT)
| 데이터 삭제(Delete)  |   DELETE   |    DELETE

<br>
<br>
<br>
<br>

**답**
<br>
<br>
㉠ : POST <br>
㉡ : 데이터 조회(Read) <br>
㉢ : UPDATE <br>

<br>
<br>

## 문제 3번

### 3. 6장 셀프체크에서 만든 <상세 페이지>에서 [수정하기] 버튼을 클릭하면 다시 <상세 페이지>를 보여주도록 구현하기**

<br>
<br>
<br>

**답**
<br>

```js
//file: MemberController.java

@GetMapping("/members/{id}/edit")
    public String edit(@PathVariable Long id, Model model){
        //수정할 데이터 가져오기
        Member memberEntity = memberRepository.findById(id).orElse(null);
        // 모델에 데이터 등록하기
        model.addAttribute("member", memberEntity);
        //뷰 페이지 설정
        return "members/edit";
    }

    @PostMapping("/members/update")
    public String update(MemberForm form){
        log.info(form.toString());
        //1.DTO 엔티티 변환
        Member memberEntity = form.toEntity();
        log.info(memberEntity.toString());

        //2. 엔티티 DB에 저장
        //2-1. DB에서 기존 데이터 가져오기
        Member target = memberRepository.findById(memberEntity.getId()).orElse(null);

        //2-2. 기존 데이터 값을 갱신하기
        if(target != null){
            memberRepository.save(memberEntity);
        }

        //3. 수정 결과 페이지로 리다이렉트
        return "redirect:/members/"+memberEntity.getId();
    }
```
<br>

```js
//file:MemberForm.java

@AllArgsConstructor
@ToString
public class MemberForm {
    private Long id;
    private String email;
    private String password;

//    public MemberForm(String email, String password) {
//        this.email = email;
//        this.password = password;
//    }
//
//    @Override
//    public String toString() {
//        return "MemberForm{" +
//                "email='" + email + '\'' +
//                ", password='" + password + '\'' +
//                '}';
//    }


    public Member toEntity() {
        return new Member(id, email, password);

    }
}
```
<br>

```js

//file: Member.java
@Getter
@NoArgsConstructor
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
                ", email='" + email + '\'' +
                ", password='" + password + '\'' +
                '}';
    }
}
```
<br>

```js
//file: show.mustache
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
    {{#members}}
        <tr>
            <th scope="row">{{id}}</th>
            <td>{{email}}</td>
            <td>{{password}}</td>
        </tr>
    {{/members}}
    </tbody>
</table>
<a href="/members/{{member.id}}/edit" class="btn btn-primary">수정하기</a>
<a href="/member">GO to Member List</a>
{{>layouts/footer}}

```

<br>

```js
//file: edit.mustache
{{>layouts/header}}

{{#member}}

<form class="container" action="/members/update" method="post">
    <input name="id" type="hidden" value="{{id}}">
    <div class ="mb-3">
        <label class ="form-label">이메일</label>
        <input type="email" class = "form-control" name ="email" value="{{email}}">
    </div>
    <div class ="mb-3">
        <label class ="form-label">비밀번호</label>
        <input type="password" class="form-control" name ="password" value="{{password}}"></textarea>
    </div>
    <button type="submit" class ="btn-primary">Submit</button>
    <a href="/members/{{id}}">Back</a>
</form>

{{/member}}

{{>layouts/footer}}
```
