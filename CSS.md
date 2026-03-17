# CSS란?

:_HTML 문서의 색상, 글꼴, 위치, 레이아웃 등 화면 표시 방식을 디자인하는 스타일 시트 언어_

> 웹페이지 꾸밀 때.
>
> > HTML이 뼈대 만들면  
> > CSS는 색, 위치를 정리해 보기 좋게 만드는 역할

## 주요 기능

- 글자 색 바꾸기
- 글자 크기 바꾸기
- 배경 색 넣기
- 가운데 정렬
- 요소 사이 간격 조절

## 예시

`color: blue;` -> 글자 파란색  
`font-size: 16px;` -> 글자 크기  
`background-color: gray;` -> 배경색  
`margin / padding` -> 여백

> CSS와 함께 쓰이는 언어 정리

<table border="2">
<tr>
<th>HTML</th>
<th>CSS</th>
<th>JavaScript</th>
</tr>
<tr>
<td>구조</td>
<td>디자인</td>
<td>동작</td>
</tr>
</table>

## 기본 개념

- **선택자**
  : 어디를 바꿀지 선택.  
  ex)  
  `p {`  
   `color: red;`  
  `}`

_모든 `<p>`태그를 빨간색으로 바꿔._
(= 같은 태그는 전부 적용됨)

- **속성**  
  : 무엇을 바꿀지. (종류)  
  ex)  
  `color`  
  _색_  
  `font-size`  
  _크기_  
  `background-color`  
  _배경색_

- **값**  
  : 어떻게 바꿀지. (결과)  
  ex)  
  `red`  
  _결과: 빨간색_  
  `16px`  
  _크키 결과: 16px_

## CSS 하는 일

- 디자인 꾸미기
- 위치 정리
- 간격 맞추기
- 배경 넣기
  :_간단한 애니메이션도 가능_

**CSS, CSS는 화면을 꾸미는 규칙**
