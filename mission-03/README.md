## 스크린샷
![missin03-gif](https://github.com/cfgop23/home-work/assets/103302206/634ce4f0-1f61-4b32-b22b-f83ce6598054)

## HTML 코드
```html
  <section class="referenceSite">
    <h2 class="siteTitle">
      <span class="siteTitle__before">관련</span>
      <span class="siteTitle__after">사이트</span>
    </h2>
    <ul class="siteListContainer">
      <li class="siteList"><a href="/" class="siteLink">제로베이스</a></li>
      <li class="siteList"><a href="/" class="siteLink">MDN</a></li>
      <li class="siteList"><a href="/" class="siteLink">웹접근성 연구소</a></li>
      <li class="siteList"><a href="/" class="siteLink">Web Standards</a></li>
      <li class="siteList"><a href="/" class="siteLink">W3C</a></li>
    </ul>
  </section>
```
## HTML 코드 설명
- 전체 영역을 section으로 설정
- section 제목을 h2태그로 관련 사이트라 명명
- span 태그로 나누어 제목 색깔 각자 지정
- 리스트를 ul태그로 묶고 각각 list를 a태그로 설정

## CSS 코드
```css
*,
*::before,
*::after {
  box-sizing: border-box;
}

body {
  margin: 0;
}

.referenceSite {
  width: 11.875rem;
  background: linear-gradient(180deg, #cccccc 0%, #eeeeee 100%);
  border: 1px solid #a3a3a3;
  border-top: 0;
  border-radius: 0 0 5px 5px;
  margin: 10rem auto;
  padding: 0.75rem;
}

.siteTitle {
  font-size: 1rem;
  margin: 0;
}

.siteTitle__after {
  color: #ed552f;
}

.siteListContainer,
.siteListContainer:hover {
  margin: 0;
  margin-top: 0.75rem;
  font-size: 0.9rem;
  list-style: none;
  background: #fff;
  border: 1px solid #a3a3a3;
  border-radius: 5px;
}

.siteListContainer {
  overflow: hidden;
  padding: 0;
  height: 1.7rem;
  transition: height 500ms 0s, padding 500ms 400ms;
}

.siteListContainer:hover {
  padding: 0.5rem 0;
  height: 9.6rem;
}

.siteLink {
  text-decoration: none;
  color: #181818;
  display: block;
  width: 100%;
  height: 1.7rem;
  line-height: 2;
  padding: 0 1.5rem;
}
```
### CSS 코드 
```css
.siteListContainer,
.siteListContainer:hover {
  margin: 0;
  margin-top: 0.75rem;
  font-size: 0.9rem;
  list-style: none;
  background: #fff;
  border: 1px solid #a3a3a3;
  border-radius: 5px;
}
```
- ul 영역에서 hover를 하기 전과 후의 공통 스타일 설정
```css
.siteListContainer {
  overflow: hidden;
  padding: 0;
  height: 1.7rem;
  transition: height 500ms 0s, padding 500ms 400ms;
}
```
- 1개의 목록만 보이게 하기 위해 높이값을 하나의 목록 길이만큼 설정하고 나머지는 보이지 않게 하기 위해 overflow:hidden 으로 설정
- transition 효과를 height와 padding 둘로 나누어 padding에 지연시간을 주고 나중에 재생되도록 설정
```css
.siteListContainer:hover {
  padding: 0.5rem 0;
  height: 9.6rem;
}
```
- hover시 height값을 지정하지 않으면 transition이 정상작동하지 않으므로 height 값을 목록 길이만큼 설정
- padding도 변해야 하므로 padding 값 역시 재설정
```css
.siteLink {
  text-decoration: none;
  color: #181818;
  display: block;
  width: 100%;
  height: 1.7rem;
  line-height: 2;
  padding: 0 1.5rem;
}
```
- a태그를 block으로 지정하여 글자 바깥영역을 클릭해도 접속할 수 있게 설정
- 높이를 지정하고 line-height 값을 높이보다 더 넓게 지정하여 높이 중앙 정렬 배치
