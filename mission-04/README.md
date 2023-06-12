# Mission 03
grid를 이용한 콘텐츠 구현하기

## 완성본
<img width="420" src="https://github.com/yxxung/home-work/assets/74893676/332d089c-3e4d-4a44-9d0e-80ff4480aa58.png"/>
<br />


## 소개
### 마크업
```
<div class="newContent">
    <div class="newContent-top-wrapper">
      <section class="newcontent-title">새소식</section>
      <a class="newcontent-more" href="/">더보기</a>
    </div>
    <div class="division"></div>
    <div class="newContent-bottom-wrapper">
      <div class="bottom-wrapper-image">
        <img src="./assets/news 1.png" alt="news" />
        <p>W3C 리뉴얼</p>
      </div>
      <div class="bottom-wrapper-paragraph">
        <h2 class="paragraph-title">W3C 사이트가 리뉴얼 되었습니다.</h2>
        <p class="paragraph-date">2022.07.18</p>
        <p class="paragraph-content">디자인 및 다양한 view 환경을 고려하여 구성되어 있으며, 기존보다 최신 정보 및 개발자를 위한 기술 가이드도 찾기 쉽도록 구성되어 있습니다.</p>
      </div>
    </div>
  </div>
```
- 구분선을 기준으로 상, 하위 wrapper로 나눴습니다.
- 하위 wrapper에서 img와 img에 대한 설명을 p태그로 나타내고 2개의 태그를 묶어줬습니다.
- 하위 wrapper에서 문단에 관련한 제목과 날짜, 내용을 한 div로 묶어줬습니다.


<br />
<br />

### CSS
```
/* 상위 wrapper */
.newContent-top-wrapper {
  font-size: 14px;
  line-height: 150%;
  display: grid;
  grid-template-columns: repeat(7, 1fr);
  grid-template-rows: auto;
}

.newcontent-title {
  font-weight: 700;
  color: #ED552F;
  grid-area: 1/1/1/2;
}

.newcontent-more {
  background: url(./assets/Union.png) no-repeat 0 50% / 14px 14px;
  display: block;
  text-align: right;
  text-decoration: none;
  font-weight: 400;
  color: #000;
  grid-area: 1/7/1/8;
}
```
- 상위 wrapper에 grid 속성을 부여하고 <secion>을 좌측 끝, <a>를 우측 끝으로 정렬해줬습니다.

```
/* 하위 wrapper */
.newContent-bottom-wrapper {
  display: grid;
  grid-template-columns: repeat(10, 1fr);
  grid-template-rows: auto;
}

.bottom-wrapper-image {
  text-align: center;
  grid-area: 1/1/1/2;
}

.bottom-wrapper-image img {
  box-shadow: 0px 15px 15px 5px #AAAAAA;
}

.bottom-wrapper-image p {
  margin: 10px 0 0 0;
  font-size: 13px;
}

.bottom-wrapper-paragraph {
  text-align: justify;
  line-height: 150%;
  grid-area: 1/3/2/11;
}

.paragraph-title {
  font-size: 13px;
  font-weight: 700;
  margin: 0;
}

.paragraph-date,
.paragraph-content {
  font-size: 12px;
  font-weight: 400;
  margin: 0;
}

.paragraph-content {
  margin-top: 12px;
}
```
- 전체 하위 wrapper에 grid 속성을 부여하고, img 관련 요소를 묶은 컨테이너(.bottom-wrapper-image)와 
  문단 관련 요소를 묶은 컨테이너(.bottom-wrapper-paragrap)를 grid의 행과 열에 맞게 정렬시켜줬습니다.
