# mission-04

> HTML

1. 전체 박스
2. 새소식 + 더보기
3. 이미지 + 이미지 제목
4. 뉴스 제목 + 날짜
5. 뉴스 내용

* 전체 박스 안에서 grid로 배치하기 위해 크게 4부분으로 구분 했습니다.
> CSS

*  전체
   *  폰트 : Pretandard
   *  font-size: 14px
   *  line-height: 21px

전체에 적용되는 폰트, 폰트사이즈, line-height는 *로 한번에 적용했습니다.

----
* container
  * display: grid
  * grid-template: auto / repeat(5,1fr)

그리드로 설정 후 row는 auto, col은 5개로 정했습니다.

----

* container--title
  * grid-area: 1/1/2/4
  
새소식 부분은 row(1,2) / col(1,4) 위치에 배치했습니다.

---
* span
  * grid-area: 1/5/2/6

+더보기 부분은 row(1,2) / col(5,6) 위치에 배치했습니다.

---
* image--box
  * grid-area: 2/1/5/3

이미지와 이미지 제목 부분은 row(2,5) / col(1,3) 위치에 배치했습니다.

---
* news
    * grid-area: 2/3/3/6

뉴스 제목과 날짜 부분은 row(2,3) / col(3,6) 위치에 배치했습니다.

---
* news--summary
  * grid-area: 4/3/6/6
  * text-align: justify

뉴스 내용 부분은 row(4,6) / col(3,6) 위치에 배치했습니다.
내용의 좌우 여백을 없애기 위해 text-align: justify를 적용했습니다.

---

> 피그마 시안을 참고해 그리드를 이용해 각 요소를 배치한 뒤 세세한 위치 조절은 margin과 padding을 이용했습니다.
