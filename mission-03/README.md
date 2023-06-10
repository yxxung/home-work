# Mission 03
transition 구현하기

## 완성본
<img width="240" src="https://github.com/yxxung/home-work/assets/74893676/a54c9d43-647e-43ea-9eb6-6023d0dbeb3f.png"/>
<br />
<img width="240" src="https://github.com/yxxung/home-work/assets/74893676/a196b683-e264-46a3-91a0-c2d19596ebfd.png"/>


## 소개
### 마크업
```
<div class="site">
    <h2 class="site__title"><span>관련 </span><span>사이트</span></h2>
    <ul class="site__list">
      <li><a href="/">제로베이스</a></li>
      <li><a href="/">MDN</a></li>
      <li><a href="/">웹접근성 연구소</a></li>
      <li><a href="/">Web Standards</a></li>
      <li><a href="/">W3C</a></li>
    </ul>
  </div>
```
- 전체 영역을 감쌀 div 박스를 먼저 만들었습니다.
- h2 태그를 이용해 제목을 나타냈습니다. 글자 색을 다르기 위해 span 태그를 이용했습니다.
- 그 밑은 ul, li 태그를 이용해 리스트를 만들었습니다.

<br />
<br />

### CSS
```
/* 드롭다운 */
.site__list {
  background: #fff;
  border: 1px solid #A3A3A3;
  border-radius: 5px;
  padding: 0 24px;
  line-height: 29px;
  max-height: 29px;
  overflow: hidden;
  transition: max-height 0.7s ease;
}

.site__list:hover {
  max-height: 145px;
  transition: all 0.5s ease-in-out;
}

.site__list a {
  display: block;
  width: 100%;
  height: 100%;
}
```
- 초기 상태에 하나의 li 태그만 나타나도록 max-height 값을 line-height와 동일하게 주었습니다.
- ul 태그에 마우스 커서를 떼도 애니메이션이 적용되도록 transition 속성을 지정했습니다.
- ul 태그에 hover 시 높이가 증가하도록 max-height 값을 145px로 지정했습니다. 또한, transition 속성을 통해 애니메이션 효과를 나타냈습니다.
- a 태그에는 display : block 속성을 통해 li 태그만큼 마우스 포인터가 잡히도록 지정했습니다.
