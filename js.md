# JavaScript 기본 문법 (JavaScript Basics)

:_웹 페이지에 동적인 기능을 추가하기 위한 프로그래밍 언어의 기본 문법_

> 데이터를 저장하고, 조건을 판단하고, 반복하고, 기능을 만드는 언어

---

## 중요성?

- 웹을 "동작"하게 만드는 핵심 언어
- 사용자와 상호작용 가능
- 프론트엔드 개발의 기본

---

## 변수 (Variable)

> 데이터를 저장하는 공간

## 선언 방법

```js
let name = "홍길동";
const age = 17;
```

## 종류

### let

- 값 변경 가능

```js
let count = 1;
count = 2;
```

---

### const

- 값 변경 불가능 (상수)

```js
const pi = 3.14;
```

## 핵심

- 기본적으로 `const` 사용
- 값이 변경될 때만 `let` 사용

---

## 조건문 (Condition)

## 개념

> 조건에 따라 다른 코드를 실행하는 구조

## 기본 구조

```
if (조건) {
  실행 코드
} else {
  실행 코드
}
```

---

## 예시

```
const age = 18

if (age >= 18) {
  console.log('성인')
} else {
  console.log('미성년자')
}
```

> 프로그램 흐름을 나누는 역할

---

## 반복문 (Loop)

> 같은 코드를 여러 번 실행

## for 문

```
for (let i = 0; i < 3; i++) {
  console.log(i)
}
```

- 반복 횟수가 정해져 있을 때 사용

---

## while 문

```
let i = 0

while (i < 3) {
  console.log(i)
  i++
}
```

- 조건이 참인 동안 반복
  > 반복 작업 자동화

## 함수 (Function)

> 특정 작업을 수행하는 코드 묶음

## 함수 선언식

```
function greet() {
  console.log('안녕하세요')
}
```

---

## 화살표 함수

```
const greet = () => {
  console.log('안녕하세요')
}
```

---

## 매개변수 / 반환값

```
function add(a, b) {
  return a + b
}
```

> 코드 재사용 가능  
>  가독성 향상

## 자료구조 (Data Structure)

> 데이터를 저장하고 관리하는 방식

---

## 배열 (Array)

### 특징

- 여러 데이터를 순서대로 저장
- 인덱스(번호)로 접근

---

### 예시

```
const fruits = ['apple', 'banana', 'orange']

console.log(fruits[0]) // apple
```

> 순서가 있는 데이터 목록

---

## 객체 (Object)

- key(이름)와 value(값)로 구성

---

### 예시

```
const user = {
  name: '홍길동',
  age: 17
}

console.log(user.name)
```

> 이름(key)으로 데이터 관리
