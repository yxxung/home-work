# Mission 02
login form 구현하기

## 완성본
<img width="320" src="https://github.com/yxxung/Frankly/assets/74893676/3477bfff-8d28-4b33-a4fb-40496528fb06"/>

## 소개
### 마크업
```
<div class="login">
    <h2 class="login__title">로그인</h2>
    <div class="login__container">
      <form action="/" class="loginForm" method="post">
        <div class="login__form__group">
          <div class="form__input__group">
            <label for="email" class="formInput__label">아이디</label>
            <input type="email" id="email" name="email" class="formInput__input" placeholder="euid@euid.dem" required />
          </div>
          <div style="height: 5.5px;"></div>
          <div class="form__input__group">
            <label for="password" class="formInput__label">비밀번호</label>
            <input type="password" id="password" name="password" class="formInput__input" placeholder="8자리 이상" required />
          </div>
        </div>
        <button type="submit" class="loginButton">로그인</button>
      </form>

      <div class="memberAccess">
        <a class="member__signup" href="/" aria-label="signup">회원가입</a>
        <a class="member__findInfo" href="/" aria-label="signin">아이디 비밀번호 찾기</a>
      </div>
    </div>
  </div>
```
- 1. 로그인(제목), 2. 아이디 레이블과 입력서식, 3. 비밀번호 레이블과 입력서식, 4. 로그인 버튼, 5. 회원가입 및 아이디/비밀번호 찾기 순으로 마크업했습니다.
- ```.login__form__group```에 로그인 기능을, ```.memberAccess```에 회원가입 및 아이디/비밀번호 찾기 를 만들어 구역을 나눴습니다.
- ```.login__form__group```은 id에 해당하는 ```.form__input__group```과 password에 해당하는 ```.form__input__group```으로 나눴습니다.

<br /><br /><br />

### CSS
```
.loginForm {
  width: 220px;
  height: 69px;
  padding: 8px;
  position: relative;
}
```
- loginForm을 button의 배치를 위한 부모 요소로 사용했습니다.
<br />

```
.loginButton {
  width: 50px;
  height: 53px;
  background-color: #ED552F;
  color: #fff;
  padding: 4px;
  border: 0;
  border-radius: 5px;
  margin-left: 8px;
  position: absolute;
  right: 8px;
  top: 50%;
  margin-top: -26px;
}
```
- button에 position: absolute; right: 8px; 을 통해 오른쪽 여백만큼 띄우고 이동 후, top: 50%, margin-top: -26px를 통해 상하 중앙 정렬을 해줬습니다.
<br />

```
.login__form__group {
  height: 61px;
  border-bottom: 1px solid #A3A3A3;
}

.form__input__group {
  width: 146px;
  height: 24px;
  position: relative;
}

.formInput__label {
  width: 56px;
  height: 24px;
  font-size: 13px;
  line-height: 21px;
  position: absolute;
  left: 0;
}

.formInput__input {
  display: block;
  width: 90px;
  height: 24px;
  line-height: 21px;
  background: transparent;
  border: 1px solid #CCCCCC;
  border-radius: 5px;
  font-size: 13px;
  position: absolute;
  right: 0;
}
.formInput__input::placeholder {
  color: #7A7A7A;
}
```
- labl과 input의 배치를 위해 ```.form__input__group```에 position: relative를 사용했습니다.
- label과 input에는 position: absolute와 각각 left: 0, right: 0 값을 주어 끝으로 배치했습니다.
- ```.login__form__group```에는 하단 구분선을 위해 8px을 제외한 만큼 높이를 주었습니다.
<br />

```
/* 회원가입, 아이디/비밀번호 찾기 */
.memberAccess {
  padding: 4px 8px;
  font-size: 13px;
}

.memberAccess a {
  height: 28px;
  line-height: 28px;
  background: url(./images/vector.png) no-repeat 0 50%/ 13px 13px;
  text-decoration: none;
  color: #181818;
  padding-left: 15px;
  font-size: 13px;
}

.member__signup {
  float: left;
}
.member__findInfo {
  float: right;
}
```
- ```.memberAccess a```에 백그라운드 이미지 삽입을 통해 꺽쇠 기호를 만들어줬으며 height와 line-height 값을 똑같이 할당하여 높이를 맞췄습니다.
- float 속성을 통해 회원가입은 왼쪽으로, 아이디/비밀번호 찾기는 오른쪽에 배치했습니다.
