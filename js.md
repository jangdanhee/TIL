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

```
let name = "홍길동";
const age = 17;
var Note = "안녕하세요.";
```

## 종류

### let

- 값 변경 가능

```
let count = 1;
count = 2;
```

---

### const

- 값 변경 불가능 (상수)

```
const pi = 3.14;
```

### var

- 값 변경 가능
  _함수 범위를 가지는 변수 선언 키워드_

```
var name = "홍길동";
name = "홍감자";
```

## 핵심

- 기본적으로 `const` 사용
- 값이 변경될 때만 `let` 사용
- 오래된 코드 유지 보수할때 사용.

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

## 일반 함수와 화살표 함수 차이

### this

일반 함수
:동적 바인딩 (dynamic binding)
호출되는 방식에 따라 this가 결정됨

화살표 함수
:정적 바인딩 (lexical binding)
함수가 만들어질 때 상위 스코프의 this로 고정

---

### Arguments

일반 함수
: arguments의 사용이 가능

화살표 함수
:화살표함수에서 사용할 경우 에러가 난다
_rest 파라미터를 사용하면 arguments 사용이 가능_

---

### 생성자함수 사용

일반 함수
:생성자 함수 사용이 가능

화살표 함수
:화살표함수에선 생성자 함수 사용이 안된다
화살표함수 내의 this가 렉시컬 스코프로 사용되기 때문에 생성자 함수내의 this로 사용이 불가능 한 것

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
