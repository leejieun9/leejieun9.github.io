---
categories: Stringboot
title: "	6장 게시글 내 페이지 이동하기"
date: 2024-05-28 00:00:03
toc: true
---
## 스프링부트 6장 실습(1)
* this list will be replaced by the table of contents
{:toc .large-only}
  <br> 
  <br>
  <br>
  <br>

## 문제 1번

<br>

### 1. 다음 ㉠~㉡에 들어갈 용어를 쓰세요.

<br>
<br>

(  ㉠  )(이)란 특정 페이지로 이동하는 HTML 태그로, 클릭 시 href 속성에 적힌 URL 주소로 요청을 보냅니다.
<br>
<br>
(  ㉡  )(이)란 컨트롤러의 특정 메서드 수행을 종료한 후 계속해서 처리할 다음 요청 주소를 지시하는 것입니다. 
<br>이를 통해 분리된 기능을 연속적인 하나의 흐름으로 연결할 수 있습니다.
<br>
​<br>
<br>
<br>

## answer
<br>

㉠ - "a <a>"   <br>
㉡ - 리다이렉트 <br>

<br>

<br>

## 문제2번
___
**3~5장 셀프체크에서 만든 <회원가입 페이지>에서 [Submit] 버튼을 클릭하면 <상세 페이지>로 이동하고,**
<br>
**<상세 페이지>에서 Go to member list를 클릭하면 <목록 페이지>로 이동하기를 구현하기**
<br>
<br>
<br>
<br>

## 답

<br>

```js
//file: MemberController.java

 Member saved = memberRepository.save(member);
        log.info(saved.toString());
        //System.out.println(saved.toString());
        return "redirect:/members/"+ saved.getId();
    }

```
<br>

```js
//file: index.mustache

    {{/memberList}}
    </tbody>
</table>
<a href="/signup">SignUP</a>
```
<br>

```js
//file: new.mustache

  </div>
    <button type="submit" class ="btn-primary">Submit</button>
    <a href="/join">Back</a>
</form>
```

<br>

```js
//file: show.mustache

</table>
<a href="/member">GO to Member List</a>

```

<br>
<br>
