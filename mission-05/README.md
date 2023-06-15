## 스크린샷
<img width="459" alt="mission05-capture" src="https://github.com/cfgop23/home-work/assets/103302206/8f0ade3b-34ba-4145-b59f-bdc631d0492d">

## HTML 코드
```html
<section class="favorite">
    <h2 class="favorite__title">
      인기 <span class="textColor">사이트</span>
    </h2>
    <ol class="favorite__list">
      <li class="favorite__item sprite spriteUp"><a href="https://www.w3.org/" target="_blank" rel="noopener noreferrer"
          class="favorite__link">W3C</a></li>
      <li class="favorite__item sprite spriteDown"><a href="https://www.webstandards.org/" class="favorite__link"
          target="_blank" rel="noopener noreferrer">Web
          Standards</a></li>
      <li class="favorite__item sprite spriteStill"><a href="https://www.csszengarden.com/" class="favorite__link"
          target="_blank" rel="noopener noreferrer">CSS
          ZenGarden</a></li>
      <li class="favorite__item sprite spriteUp"><a href="https://developer.mozilla.org/ko/" target="_blank"
          rel="noopener noreferrer" class="favorite__link">MDN</a></li>
    </ol>
    <a href="#" class="favorite__more">
      <span class="plus">+</span>
      더보기
    </a>
  </section>
```

## HTML 코드 설명
- 전체영역을 section으로 설정
- 인기 사이트 제목을 h2태그로 처리
- 사이트 목록을 순서목록으로 정의하기 위해 ol태그로 설정
- li 태그 안에 a 태그를 넣어 해당 링크로 바로갈 수 있게 처리
- 링크는 새탭에 열 수 있게 target을 _blank 처리하고 보안 이슈 문제를 피하기 위해 rel 속성에 "noopener noreferrer" 값 설정
- 더보기 링크 설정

## CSS 코드 설명
```css
.favorite {
  margin: 100px auto 0;
  width: 11.875rem;
  padding: 0.75rem;
  background: linear-gradient(180deg, #cccccc 0%, #eeeeee 100%);
  border: 1px solid #a3a3a3;
  border-radius: 5px;
  position: relative;
}
```
- 더보기 링크를 position:absolute 로 처리하기 위해 상위 요소에 기준이 될 수 있게 position: relative 부여
```css
.favorite__list {
  list-style: none;
  margin: 0;
  margin-top: 0.5rem;
  padding-left: 0;
  font-size: 0.75rem;
}
```
- 순서목록에서 기본숫자가 보이지 않게 list-style: none 을 줘서 처리
```css
.favorite__item {
  counter-increment: number;
  margin: 0.5rem 0 0 0;
  display: flex;
  flex-flow: row nowrap;
  align-items: center;
}

.favorite__item::before {
  content: counter(number);
  display: inline-block;
  width: 1rem;
  height: 1rem;
  text-align: center;
  line-height: 1.1rem;
  background: #a3a3a3;
  color: #fff;
  border-radius: 5px;
  margin-right: 4px;
  padding: 1px;
}
```
- css로 숫자를 보이게 하기 위해 counter-increment: number 주고 ::before 가상선택자 content에 counter(number) 함수를 줘서 리스트당 하나씩 증가하는 숫자 생성
- 리스트 중앙정렬을 위해 flex를 주고 align-items: center 설정
- 숫자 영역 스타일을 위해 inline-block을 주고 꾸밈
```css
.favorite__link {
  display: block;
  width: 100%;
}
```
- 링크 글자 외부를 클릭해도 해당 사이트로 들어 갈 수 있게 block으로 설정하고 길이 100%로 늘림
```css
.favorite__more {
  font-size: 0.875rem;
  position: absolute;
  top: 0.75rem;
  right: 0.75rem;
  display: flex;
  flex-flow: row nowrap;
  align-items: center;
}
```
- 마크업 상 맨 밑에 있던 더보기 링크를 맨 위로 끌어올리기 위해 position:absolute를 주고 top, right 속성 설정
- +기호와 글자 간 중앙정렬을 위해 flex를 주고 align-items:center 설정
