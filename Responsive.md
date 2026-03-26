# 반응형이란? (Responsive)

:_다양한 화면 크기에 맞게 웹페이지가 자동으로 변화하는 설계 방식_

> 화면 크기에 따라 구조와 스타일이 바뀌는 기술

---

## 팔요성

- 기기마다 화면 크기가 다름
- 가독성과 사용성을 유지하기 위해 필요

---

## 핵심 개념

- 하나의 코드로 여러 환경 대응
- 화면 크기에 따라 레이아웃과 요소 크기 변화

---

## Media Query

### 개념

- 조건에 따라 CSS 적용

```
@media (조건) {
  스타일
}
```

---

## 반응형 단위

- `%` : 부모 기준
- `vw` : 브라우저 창의 너비 기준
- `vh` : 브라우저 창의 높이 기준
- `rem` : 글자 기준

> 고정(px)이 아닌 비율 기반 사용

---

# 레이아웃 (Layout)

:_웹 요소를 어떻게 배치할지 정하는 방식_

---

# Flex (Flexbox)

> 한 방향(1차원) 정렬

---

## 기본 사용

```
.container {
  display: flex;
}
```

---

## 정렬

```
justify-content: center; /* 가로 */
align-items: center;     /* 세로 */
```

> 한 줄 정렬에 적합

---

# Grid (CSS Grid)

## 핵심

- 행 + 열 (2차원) 레이아웃

---

## 기본 사용

```
.container {
  display: grid;
}
```

---

## 구조 설정

```
grid-template-columns: 1fr 1fr;
grid-template-rows: 100px 200px;
```

> 전체 레이아웃 복잡한 구성에 적합

# Flex vs Grid 차이

- Flex -> 한 줄 정렬 (콘텐츠 중심)
- Grid -> 전체 구조 설계 (레이아웃 중심)
