# DOM이란?

:_웹 브라우저가 HTML 문서를 해석하여, JavaScript로 조작할 수 있도록 만든 트리(Tree) 구조의 객체 모델_

> HTML을 코드로 조작 가능하게 만든 구조

---

### 왜 필요한가?

HTML만으로는 정적인 화면만 만들 수 있음  
→ JavaScript를 이용하면 동적인 웹페이지 구현 가능

ex)

- 버튼 클릭 시 내용 변경
- 입력값에 따라 실시간 반응
- 새로운 요소 생성 및 삭제

---

# 요소 선택 (Selection)

- HTML에서 원하는 요소를 찾아오는 과정.

## 주요 메서드

### document.querySelector

- CSS 선택자 방식
- 하나의 요소만 선택

```
document.querySelector(".box");
```

---

### document.querySelectorAll

- 조건에 맞는 모든 요소 선택
- NodeList 형태 (유사 배열)

```
document.querySelectorAll(".box");
```

---

> 어떤 요소를 가져올 것인지가 가장 중요

---

# 요소 생성&수정

## 개념

- 새로운 요소를 만들거나 기존 요소를 변경하는 작업.

---

## 요소 생성

### createElement

- 새로운 HTML 요소 생성

```
const div = document.createElement("div");
```

---

## 요소 추가

### appendChild

- 부모 요소에 자식 요소 추가

```
document.body.appendChild(div);
```

---

## 요소 내용 변경

### innerHTML

- HTML 태그까지 포함해서 내용 변경

```
div.innerHTML = "<b>굵은 글씨</b>";
```

---

### textContent

- 텍스트만 변경 (태그 적용 X)

```
div.textContent = "일반 텍스트";
```

---

# DOM 조작 흐름

## 기본 흐름

1. 요소 선택
2. 요소 생성 (필요한 경우)
3. 내용 수정
4. DOM에 추가

---

## 예시 흐름 코드

```
const box = document.querySelector("#box");

const newEl = document.createElement("p");
newEl.textContent = "추가된 요소";

box.appendChild(newEl);
```

---

# DOM 조작의 핵심 개념

## 1. 선택 → 수정 → 반영

- DOM 조작은 항상 이 흐름을 따름

## 2. 모든 것은 객체(Object)

- HTML 요소도 JavaScript 객체처럼 다룸

## 3. 구조 기반 접근

- 부모 / 자식 관계를 이해해야 함

---
