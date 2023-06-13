## 스크린샷
<img width="737" alt="misson04" src="https://github.com/cfgop23/home-work/assets/103302206/934330fc-07b3-4dee-aef1-473ce0ecc05c">

## HTML 코드
```html
  <section class="news">
    <header class="newsHeader">
      <h2 class="newsHeading">새소식</h2>
      <a href="#더보기" class="newsMore"><span class="plusIcon">+</span><span>더보기</span></a>
    </header>
    <a href="#해당게시글" class="newsLink">
      <article class="newsArticle">
        <div class="newsContainer">
          <h3 class="newsTitle">W3C 사이트가 리뉴얼 되었습니다.</h3>
          <time datetime="2022-07-18" class="newsDate">2022.07.18</time>
          <p class="newsDesc">디자인 및 다양한 view 환경을 고려하여 구성되어 있으며, 기존보다 최신 정보 및 개발자를 위한 기술 가이드도 찾기 쉽도록 구성되어 있습니다.</p>
        </div>
        <figure class="newsThumbnail">
          <img src="images/news.png" alt="리뉴얼된 W3C 사이트" />
          <figcaption>W3C 리뉴얼</figcaption>
        </figure>
      </article>
    </a>
  </section>
```
## HTML 코드 설명 
- 전체 영역을 section으로 설정
- section 내부에 header를 두고 header 안에 h2태그로 section 제목 설정
- 더보기는 a태그로 감싸 링크로 설정
- 게시글 영역을 article로 설정하고 그 밖을 a태그로 감싸 게시글을 클릭하면 해당 게시글로 이동할 수 있게 설정
- 게시글 영역은 독립적으로 사용할 수 있는 영역이라 판단하여 article 태그 사용
- h3태그로 article 및 게시글 제목으로 설정
- time태그로 날짜의미를 지니게 설정
- 이미지와 이미지 설명란을 구분하여 쓰기 위해 figure와 figcaption 태그 사용

## CSS 코드
```css
*,
*::before,
*::after {
  box-sizing: border-box;
}

body {
  margin: 0;
  color: #181818;
}

a {
  text-decoration: none;
  color: #181818;
}

.news {
  width: 23.75rem;
  margin: 10rem auto;
  display: grid;
  gap: 10px;
  grid-template-columns: 1fr 1fr;
  grid-template-rows: auto;
  font-size: 0.875rem;
}

.newsHeader {
  grid-area: 1 / 1 / 2 / 3;
  display: flex;
  flex-flow: row wrap;
  justify-content: space-between;
  align-items: end;
}

.newsHeading {
  margin: 0;
  color: #ed552f;
  font-size: 1rem;
}

.newsMore {
  display: flex;
  flex-flow: row nowrap;
  align-items: end;
}

.plusIcon {
  color: #447231;
  font-size: 2rem;
  line-height: 0.5;
  font-weight: 900;
  margin-right: 0.2rem;
}

.newsHeader::after {
  content: "";
  margin: 0.75rem 0;
  width: 100%;
  height: 1px;
  background: linear-gradient(90deg, #a9a9a9 -1.32%, #ffffff 100%);
}

.newsLink {
  grid-area: 2 / 1 / 3 / 3;
}

.newsArticle {
  display: grid;
  grid-template-columns: 7rem 1fr;
  gap: 1rem;
}

.newsContainer {
  grid-area: 1 / 2 / 3 / 3;
}

.newsTitle {
  margin: 0;
  margin-bottom: 0.5rem;
  font-size: inherit;
}

.newsDesc {
  line-height: 1.6;
  margin: 0;
  margin-top: 0.7rem;
  text-align: justify;
}

.newsThumbnail {
  margin: 0;
  grid-area: 1 / 1 / 3 / 2;
}

.newsThumbnail img {
  width: 100%;
  box-shadow: 0px 15px 15px 5px #aaaaaa;
}

.newsThumbnail figcaption {
  text-align: center;
  margin-top: 0.8rem;
}
```
## CSS 코드 설명
```css
.news {
  width: 23.75rem;
  margin: 10rem auto;
  display: grid;
  gap: 10px;
  grid-template-columns: 1fr 1fr;
  grid-template-rows: auto;
  font-size: 0.875rem;
}
```
- section 영역을 grid로 설정하고 header 영역과 article 영역을 위아래로 배치
```css
.newsHeader::after {
  content: "";
  margin: 0.75rem 0;
  width: 100%;
  height: 1px;
  background: linear-gradient(90deg, #a9a9a9 -1.32%, #ffffff 100%);
}
```
- header 영역과 article 영역 구분선을 header 태그의 after 가상선택자로 만들어 구분선 스타일링
 ```css
 .newsArticle {
  display: grid;
  grid-template-columns: 7rem 1fr;
  gap: 1rem;
}
```
- article 내부 역시 grid로 설정하고 figure 영역을 왼쪽에 배치하고 나머지를 오른쪽에 배치

 ```css역
 ```css
 .newsDesc {
  line-height: 1.6;
  margin: 0;
  margin-top: 0.7rem;
  text-align: justify;
}
```
- 글내용을 양쪽 정렬
