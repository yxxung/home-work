# Mission 05
sprite 기법을 활용한 콘텐츠 구현하기

## 완성본
<img width="320" src="https://github.com/yxxung/home-work/assets/74893676/a42a7dae-c637-4626-b2e5-a74fd1dc0343.png"/>
<br />


## 소개
### 마크업
```
<section class="favorite">
    <h2 class="favorite__title">인기 <span>사이트</span></h2>
    <ol class="favorite__list">
      <li class="w3c"><a href="/">W3C</a></li>
      <li class="web"><a href="/">Web Standards</a></li>
      <li class="css"><a href="/">CSS ZenGarden</a></li>
      <li class="mdn"><a href="/">MDN</a></li>
    </ol>
    <a class="favorite__more" href="/">더보기</a>
</section>
```
- 전체 영역을 section, 그 아래에 제목을 나타내는 h2와 a태그인 더보기, 인기 사이트 리스트는 ol > li 로 마크업했습니다.
- 사이트 이동이 가능하게 li 태그 안 a 태그를 사용했습니다.


<br />
<br />

### CSS
#### 더보기
```
.favorite {
  width: 190px;
  background: linear-gradient(180deg, #CCCCCC 0%, #EEEEEE 100%);
  border: 1px solid #A3A3A3;
  border-radius: 5px;
  color: #181818;
  padding: 12px;
  position: relative;
}

.favorite__more {
  font-size: 15px;
  font-weight: 500;
  line-height: 150%;
  text-decoration: none;
  position: absolute;
  top: 12px;
  right: 12px;
  color: #181818;
  background: url(./assets/Union.png) no-repeat 0 50%;
  padding-left: 20px;
}
```
- 전체 영역에 position: relative 속성을 부여하여 더보기 영역이 우측 상단에 위치할 수 있도록 했습니다.

<br />

#### 리스트 - ol
```
.favorite__list {
  display: flex;
  flex-flow: column nowrap;
  list-style: none;
  padding: 0;
  margin: 8px 0 0 0;
  gap: 8px;
}
```
- 전체 리스트를 감싸는 ol에 flex 속성을 주어 수직으로 정렬해주었습니다.

<br />

#### 리스트 - li
```
.favorite__list {
  display: flex;
  flex-flow: column nowrap;
  list-style: none;
  padding: 0;
  margin: 8px 0 0 0;
  gap: 8px;
}

.favorite__list li {
  display: flex;
  flex-flow: row nowrap;
  justify-content: space-between;
  align-items: center;
}

.favorite__list li a {
  flex-grow: 2;
  padding-left: 4px;
  line-height: 150%;
  font-size: 14px;
  text-decoration: none;
  color: inherit;
}
```
- li의 아이템은 총 3개입니다. 1. list-style을 나타내는 ::before, 2. 각 사이트들을 나타내는 a, 3. 랭킹의 업다운을 표시해주는 ::after
- 세 개의 아이템을 정렬해주기 위해 li에 flex 속성을 부여하고 row 기준으로 정렬해줬습니다.
- ::before와 ::after를 양 끝에 배치하기 위해 justify-content: space-between을 사용했습니다.
- 또한 상하 중앙 정렬을 위해 align-items: center를 사용했습니다.

- 여기까지 정렬할 경우, a태그의 크기 만큼을 제외하고 자동으로 양쪽 여백이 생기게 됩니다.
- 그 여백만큼을 없애고 ::before 옆에 위치시키기 위해 flex-grow를 사용해 남은 영역의 크기를 갖게 했습니다.
- 마지막으로 padding-left: 4px를 주어 주어진 여백만큼 띄워주었습니다.

<br />

#### list-style
```
.favorite__list li::before {
  width: 12px;
  height: 12px;
  background: #A3A3A3;
  border-radius: 7px;
  color: #fff;
  padding: 4px;
  text-align: center;
  font-size: 11px;
  line-height: 110%;
}

.w3c::before {
  content: "1";
}
.web::before {
  content: "2";
}
.css::before {
  content: "3";
}
.mdn::before {
  content: "4";
}
```
- list-style을 새로 만들기 위해 기존 리스트 스타일은 없애고 ::before를 이용해 새로 만들어줬습니다.
- 공통 스타일로 리스트 스타일을 만들고, 각 li태그 마다 content 속성을 이용해 번호를 넣어줬습니다.

<br />

#### ranking
```
.favorite__list li::after {
  content: "";
  display: block;
  width: 9px;
  height: 11px;
  background-image: url(./assets/rank.png);
}

.w3c::after {
  background-position: 0 0;
}

.web::after {
  background-position: 0 -44.5px;
}

.css::after {
  background-position: 0 -22.25px;
}

.mdn::after {
  background-position: 0 0;
}
```
- ::after를 이용해 background-image로 rank 이미지를 삽입 후, sprite 기법을 이용해 스타일링 해줬습니다.
- 각 요소의 길이를 9.5px, 각 여백을 12.75px로 계산하여 backgound-position을 통해 위치를 이동시켰습니다.
