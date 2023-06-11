# 과제 3
### 시멘틱 마크업
> div.margin__box : 전체 박스 (회색) <br>
> section.box : 내부 박스 (흰색)<br>
> h2 : 제목 <br>
> div.box__link : 링크 박스 <br>
> ul : 리스트 모음 <br>
> li+a : 각 리스트 링크로 

### CSS
- base.css import해서 css 초기화
- Pretendard font 불러오기
- 전체 박스 크기 및 배경 그라데이션 효과
- h2태그 안에서 글자 색 다르게 하기 위해 span으로 따로 묶어줌
- 마우스 올라갔을 때 리스트 늘어나는 애니메이션 (:hover 사용)
  - transition: height 300ms
  - 반대 상황도 똑같이 해주기 위해 transition-timing-function 사용
- margin, padding은 피그마 시안 참조.
  