스크린샷 

<img width="816" alt="mission02-capture" src="https://github.com/cfgop23/home-work/assets/103302206/25e2effc-5f8a-4d33-b30e-ecd4c92c5e44">

```html
<!DOCTYPE html>
<html lang="ko">

<head>
  <meta charset="UTF-8" />
  <meta http-equiv="X-UA-Compatible" content="IE=edge" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>position 과제</title>
  <link rel="stylesheet" href="login.css" />
</head>

<body>
  <div class="wrapper">
    <h1>position 과제</h1>
    <div class="loginWrapper">
      <h2 class="loginTitle">로그인</h2>
      <form action="/" class="loginForm" method="post">
        <fieldset>
          <legend class="a11y">로그인 폼</legend>
          <div class="loginFormContainer">
            <div class="inputContainer">
              <label for="userId" class="inputContainer__label">아이디</label>
              <input type="email" class="inputContainer__input" id="userId" name="userId" placeholder="euid@euid.com"
                required />
            </div>
            <div class="inputContainer">
              <label for="userPassword" class="inputContainer__label">비밀번호</label>
              <input type="password" class="inputContainer__input" id="userPassword" name="userPassword"
                placeholder="8자리 이상" required />
            </div>
            <button type="submit" class="loginBtn">로그인</button>
          </div>
          <div class="memberService" aria-label="회원 서비스">
            <div class="memberService__memberContainer">
              <span class="arrow">&gt;</span>
              <span class="memberSubject">회원가입</span>
            </div>
            <div class="memberService__findIdPassword">
              <span class="arrow">&gt;</span>
              <span class="memberSubject">아이디 비밀번호 찾기</span>
            </div>
          </div>
        </fieldset>
      </form>
    </div>
  </div>
</body>

</html>
```
#### HTML 코드설명
- div.wrapper : 결과물을 보기좋게 가운데 배치하기 위해 사용된 태그
- h2 : 로그인 제목
- 로그인 정보를 서버에 보내기 위해 form 태그 사용, form 태그안에 요소를 묶고 어떤 내용인지 알려주기 위해 fieldset, legend를 사용
- label과 input태그를 묶기 위해 div.inputContainer로 감쌌음
- 아이디 input의 타입은 email로 지정, 비밀번호 input의 타입은 password로 지정, 두 태그 모두 반드시 값이 있어야 하므로 required 지정,
서버에 보낼 데이터 필드 이름을 위해 name 속성 지정
- 버튼 타입은 로그인 데이터를 서버로 보내기 위해 submit 지정
- 접근성을 위해 멤버서비스 div를 묶어 aria-label를 넣어 회원서비스로 명명
- div.memberContainer와 div.findIdPassword로 회원가입과 아이디 비밀번호 찾기를 각각 묶음

```css
* {
  box-sizing: border-box;
}

body {
  margin: 0;
}

fieldset {
  border: 0;
  margin: 0;
  padding: 0;
}

.a11y {
  position: absolute;
  width: 1px;
  height: 1px;
  margin: -1px;
  overflow: hidden;
  visibility: hidden;
  clip: rect(0, 0, 0, 0);
  clip-path: inset(50%);
}

.wrapper {
  width: 500px;
  margin: 5rem auto;
}

.loginWrapper {
  width: 15.25rem;
  background: linear-gradient(90deg, #ed552f 0%, #e8852e 100%);
  border: none;
  border-radius: 5px;
  box-shadow: 5px 5px 0 #aaa;
  padding: 0.75rem;
}

.loginTitle {
  margin: 0;
  margin-bottom: 0.5rem;
  color: #ffff00;
  font-size: 1rem;
  font-weight: 700;
}

.loginForm {
  background-color: #fff;
  padding: 0.5rem;
  padding-bottom: 0.25rem;
  border-radius: 5px;
}

.loginFormContainer {
  position: relative;
  height: 3.25rem;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
}

.inputContainer__label {
  display: inline-block;
  width: 3.5rem;
  font-size: 0.875rem;
}

.inputContainer__input {
  width: 5.625rem;
  height: 1.5rem;
  border: 1px solid #ccc;
  border-radius: 5px;
  padding-left: 0.5rem;
}

.loginBtn {
  position: absolute;
  top: 0;
  right: 0;
  height: 3.25rem;
  color: #fff;
  background: #ed552f;
  border: none;
  border-radius: 5px;
  cursor: pointer;
}

.memberService {
  margin-top: 0.5rem;
  padding-top: 0.25rem;
  border-top: 1px solid #ccc;
  display: flow-root;
  font-size: 0.82rem;
}

.memberService__memberContainer {
  float: left;
  display: flex;
  align-items: center;
}

.memberService__findIdPassword {
  float: right;
  display: flex;
  align-items: center;
}

.arrow {
  color: #ed552f;
  font-size: 1.2rem;
  font-weight: 900;
}

.memberSubject {
  margin-left: 0.25rem;
}
```

### CSS 코드설명
```css
fieldset {
  border: 0;
  margin: 0;
  padding: 0;
}

.a11y {
  position: absolute;
  width: 1px;
  height: 1px;
  margin: -1px;
  overflow: hidden;
  visibility: hidden;
  clip: rect(0, 0, 0, 0);
  clip-path: inset(50%);
}
```
- fieldset을 화면상에 표시하지 않기 위한 코드 작성
- 접근성을 위해 적은 코드지만 화면상에 표시하지 않기 위한 a11y 클래스

```css
.loginWrapper {
  width: 15.25rem;
  background: linear-gradient(90deg, #ed552f 0%, #e8852e 100%);
  border: none;
  border-radius: 5px;
  box-shadow: 5px 5px 0 #aaa;
  padding: 0.75rem;
}
```
- 배경색 그라데이션 효과를 위해 linear-gradient 속성 사용

```css
.loginFormContainer {
  position: relative;
  height: 3.25rem;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
}
```
- 로그인 버튼을 position: absolute 속성을 이용해 배치하기 위해 position: relative로 기준 설정
- input 입력창을 위,아래로 만들고 간격을 벌리기 위해 flex, column, space-between 사용

```css
.inputContainer__label {
  display: inline-block;
  width: 3.5rem;
  font-size: 0.875rem;
}
```
- label과 input 입력창의 양끝 배치를 위해 사용

```css
.loginBtn {
  position: absolute;
  top: 0;
  right: 0;
  height: 3.25rem;
  color: #fff;
  background: #ed552f;
  border: none;
  border-radius: 5px;
  cursor: pointer;
}
```
- 로그인 버튼을 오른쪽에 배치하기 위한 코드

```css
.memberService {
  margin-top: 0.5rem;
  padding-top: 0.25rem;
  border-top: 1px solid #ccc;
  display: flow-root;
  font-size: 0.82rem;
}
```
- 멤버서비스 요소들을 float로 배치했기 때문에 부모요소를 끌어올리기 위한 flow-root 작성

```css
.memberService__memberContainer {
  float: left;
  display: flex;
  align-items: center;
}

.memberService__findIdPassword {
  float: right;
  display: flex;
  align-items: center;
}
```
- 회원가입 영역은 float:left로 왼쪽 배치, 아이디 비밀번호 찾기 영역은 right로 오른쪽 배치
- 화살표와 텍스트의 중앙정렬을 위해 flex를 주고 align-items를 center로 작성








