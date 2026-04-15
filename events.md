# 이벤트 처리란?

:_사용자의 행동이나 브라우저에서 발생하는 변화를 감지하고, 그에 따라 동작을 실행하는 메커니즘_

> 이벤트가 발생하면 -> 지정한 함수 실행

---

## 필요성?

정적인 웹페이지 -> 사용자와 상호작용 불가능  
이벤트를 사용하면 -> 동적인 웹 구현 가능

ex)

- 버튼 클릭 시 동작 실행
- 입력값에 따라 실시간 처리
- 선택 변경 시 화면 업데이트

---

# 이벤트 (Event)

- 사용자 행동 또는 브라우저에서 발생하는 변화# 이벤트 처리 (Event Handling)

:_사용자의 행동이나 브라우저에서 발생하는 변화를 감지하고, 그에 따라 동작을 실행하는 메커니즘_

> 사용자 행동 또는 브라우저에서 발생하는 변화

---

ex)

- 클릭(click)
- 입력(input)
- 값 변경(change)

---

# 이벤트 리스너 (Event Listener)

> 특정 이벤트가 발생했을 때 실행할 함수를 등록하는 방법

---

## addEventListener

### 역할

- 요소에 이벤트와 실행 함수를 연결

---

### 기본 구조

```
요소.addEventListener("이벤트종류", 함수);
```

---

### 예시

```
const btn = document.querySelector("#btn");

btn.addEventListener("click", function () {
  console.log("클릭됨");
});
```

---

# 3. 주요 이벤트

## click

- 요소를 클릭했을 때 발생

```
btn.addEventListener("click", () => {
  console.log("클릭");
});
```

---

## input

- 입력값이 바뀔 때마다 실시간 발생

```
input.addEventListener("input", () => {
  console.log("입력 중");
});
```

---

## change

- 입력이 끝나고 값이 확정될때 발생

```
input.addEventListener("change", () => {
  console.log("입력 완료");
});
```

---

# 이벤트 객체 (Event Object)

> 이벤트 발생 시 자동으로 생성되는 객체.
> 이벤트 관련 정보를 담고있음.

---

## event

### 역할

- 이벤트에 대한 다양한 정보 제공

```
btn.addEventListener("click", function (event) {
  console.log(event);
});
```

---

## event.target

### 역할

- 실제 이벤트가 발생한 요소를 가리킴

```
btn.addEventListener("click", function (event) {
  console.log(event.target);
});
```

---

## 예시 흐름 코드

```
const btn = document.querySelector("#btn");

btn.addEventListener("click", function (event) {
  console.log("클릭됨");
  console.log(event.target);
});
```

---

# 이벤트 처리 핵심 개념

## 1. 이벤트 기반 동작

- 사용자의 행동에 따라 코드 실행

## 2. 함수 실행 구조

- 이벤트 발생 시 등록된 함수가 실행됨

## 3. event 객체 활용

- 이벤트 정보를 활용해 더 정밀한 제어 가능
