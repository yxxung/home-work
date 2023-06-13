# Mission 04
grid를 이용한 콘텐츠 구현하기

## 완성본
<img width="420" src="https://github.com/yxxung/home-work/assets/74893676/3a49779f-b746-4bc0-a143-9a474545e2b8.png"/>
<br />


## 소개
### 마크업
```
<div class="news">
    <section class="news-title">새소식</section>
    <a class="news-more" href="/">더보기</a>

    <div class="division"></div>

    <div class="news-image-wrapper">
      <img src="./assets/news 1.png" alt="news-image" />
      <p>W3C 리뉴얼</p>
    </div>

    <div class="news-paragraph-wrapper">
      <h2 class="paragraph-title">W3C 사이트가 리뉴얼 되었습니다.</h2>
      <p class="paragraph-date">2022.07.18</p>
      <p class="paragraph-content">디자인 및 다양한 view 환경을 고려하여 구성되어 있으며, 기존보다 최신 정보 및 개발자를 위한 기술 가이드도 찾기 쉽도록 구성되어 있습니다.</p>
    </div>
  </div>
```
- news에 diplay: grid; 속성을 줄 것입니다. 따라서 총 5개의 콘텐츠로 나눴습니다.
- 새소식, 더보기, 구분선, 이미지 컨테이너, 글 컨테이너로 나눴습니다.


<br />
<br />

### CSS
#### 전체 영역
```
.news {
  width: 380px;
  color: #181818;
  display: grid;
  grid-template-columns: repeat(10, 1fr);
  grid-template-rows: auto;
  gap: 1px
}
```
- 전체 영역에 grid 속성을 부여하고 총 width가 380px 이므로, .news-title에 해당하는 37px와 gap: 1px를 설정하여 총 10칸으로 나눴습니다.

<br />
#### 새소식, 더보기
```
.news-title {
  font-weight: 700;
  color: #ED552F;
  grid-area: 1/1/2/2;
  font-size: 13px;
  line-height: 150%;
}

.news-more {
  font-size: 13px;
  font-weight: 400;
  line-height: 150%;
  text-decoration: none;
  color: #000;
  grid-area: 1/10/2/11;
  position: relative;
}

.news-more::before {
  content: url(./assets/Union.png);
  position: absolute;
  height: 16px;
  top: 2px;
  right: 41px;
}
```
- 그리드 시스템 위치에 맞게 grid-area 속성을 이용해 배치해줬습니다.
- 더보기의 +버튼은 a태그에 직접적으로 background-image로 삽입 시 요소 width가 늘어나 grid 시스템을 벗어나게 됩니다. 따라서 before 가상 요소 선택자를 이용해 content로 삽입 후 position으로 위치를 조정해줬습니다.

<br />
#### 이미지 컨테이너
```
.news-image-wrapper {
  text-align: center;
  grid-area: 3/1/4/4;
  margin-top: 12px;
}

.news-image-wrapper img {
  box-shadow: 0px 15px 15px 5px #AAAAAA;
}

.news-image-wrapper p {
  margin: 10px 0 0 0;
  font-size: 13px;
}
```
- 이미지와 이미지에 대한 설명을 감싸는 전체 컨테이너에 grid-area 속성을 주어 배치했습니다.

<br />
#### 글 컨테이너
```
.news-paragraph-wrapper {
  text-align: justify;
  line-height: 150%;
  grid-area: 3/4/4/11;
  margin: 12px 0 0 12px;
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
- 이미지 컨테이너와 마찬가지로 전체 text 요소들을 감싸는 wrapper를 만들고 grid 시스템에 맞게 배치해줬습니다.
