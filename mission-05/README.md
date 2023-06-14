# mission-05-sprite

## 1. 완성본
<img width="406" alt="sprite" src="https://github.com/whddbsl/home-work/assets/130979302/cfa7cc8b-94cf-4e99-8a0d-7e4ccfb09c6f">

---
## 2. 마크업
### 마크업 순서
1. 인기 사이트
2. 인기사이트 리스트
3. 더보기

> 순서가 있는 리스트이므로 ol을 사용했고 랭킹 변화 상태는 각 리스트(li)의 background로 넣어주었습니다.

### HTML 코드
``` html
<section class="site">
        <h2 class="site__title">인기 <span>사이트</span></h2>
        <section class="site__item">
            <ol class="item__list">
                <li class="sprite spriteW3C">W3C</li>
                <li class="sprite spriteWeb">Web Standards</li>
                <li class="sprite spriteCSS">CSS ZenGarden</li>
                <li class="sprite spriteMDN">MDN</li>
            </ol>
        </section>
        <a href="/" class="site__more"><span class="plus">+</span> 더보기</a>
    </section>
```
---

## 3. CSS
1. `인기 사이트` 가 전체 타이틀로 들어가 있는데 `사이트` 부분 글자 색을 바꿔주기 위해 `span`으로 사이트만 따로 묶어줬습니다. 
2. 더보기 부분 마크업을 제일 마지막에 했지만 오른쪽 상단에 위치시키기 위해 상위 요소인 `.site`에 `position: relative`를 주고 `.site__more`에 `position: absolute`를 준 뒤  `top`, `right`를 이용했습니다.
3. 각 리스트 위아래 간격을 벌려주기 위해 `display: flex`, `flex-direction: column`, `gap: 8px`를 줬습니다.
4. 랭킹 이미지가 sprite 형식이므로 각 리스트에 `sprite` 클래스를 주고 공통 속성을 먼저 줬습니다
5. 리스트별 알맞는 이미지를 주기 위해 `background-position`을 이용했습니다. 리스트 가장 우측에 이미지를 배치하기 위해 x좌표는 `right`를 주고 y좌표는 각 이미지별 알맞는 좌표를 줬습니다.
6. 리스트 앞에 순위를 주기 위하여 먼저 `sprite` 클래스에 `before 가상요소`를 부여하여 회색 배경을 만들어 주었습니다.
7. 그 후, 각 리스트별 랭킹에 맞는 숫자를 `content`에 줬습니다.

### CSS 코드
``` css
/* css 초기화 */
@import url(base.css);
/* @import url(reset.css); */

/* 폰트 설정 */
@font-face {
    font-family: 'Pretendard-Regular';
    src: url('https://cdn.jsdelivr.net/gh/Project-Noonnu/noonfonts_2107@1.1/Pretendard-Regular.woff') format('woff');
    font-weight: 400;
    font-style: normal;
}

* {
    font-family: 'Pretendard-Regular';
}

body{
    margin: 50px;
}

.site{
    position: relative;
    width: 190px;
    background: linear-gradient(180deg, #CCCCCC 0%, #EEEEEE 100%);
    border: 1px solid #a3a3a3;
    border-radius: 5px;
    padding: 12px;
}

.site__title{
    font-size: 15px;
    line-height: 150%;
    font-weight: 700;
    margin-bottom: 8px;
}

.site__title span{
    color: #ed552f;
}

.site__more{
    position: absolute;
    top: 12px;
    right: 12px;
    font-size: 14px;
    line-height: 150%;
    font-weight: 400;
}

.item__list{
    display: flex;
    flex-direction: column;
    padding: 0;
    margin-left: 20px;
    gap: 8px;
    line-height: 150%;
    font-size: 11px;
    font-weight: 400;
}


.sprite
{
    background: url(rank.png) no-repeat;
    list-style: none;
}

.spriteW3C{
    background-position: right 3px 
}

.spriteWeb{
    background-position: right -42px;
}

.spriteCSS{
    background-position: right -19.5px;
}

.spriteMDN{
    background-position: right -42px;
}

.sprite::before{
    content: "";
    color: white;
    background: #a3a3a3;
    border-radius: 5px;
    height: 16px;
    width: 16px;
    position: absolute;
    left: 12px;
    padding-left: 5px;
}

.spriteW3C::before{
    content: "1";
}

.spriteWeb::before{
    content: "2";
}

.spriteCSS::before{
    content: "3";
}

.spriteMDN::before{
    content: "4";
}

.plus{
    position: absolute;
    font-size: 30px;
    color: green;
    right: 40px;
    top: -3px;
}
```