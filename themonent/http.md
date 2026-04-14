# HTTP란?

:_Hyper Text Transfer Protocol의 약자로, World Wide Wed 상에서 데이터를 주고받기 의한 **통신 규약(프로토콜)**._

> HTTP는 클라이언트와 서버 간의 요청과 응답을 통해 작동한다.

<br>

### 웹에서의 역할

- 브라우저(클라이언트)가 웹 서버에 **요청(Request)** 을 보내고, 서버가 **응답(Response)** 을 돌려주는 방식으로 동작한다.
- HTML, CSS, JavaScript, 이미지, JSON 등 **모든 웹 리소스**의 전송에 사용된다.
- 기본 포트는 **80번(HTTP)**, 암호화된 버전인 HTTPS는 **443번**을 사용한다.

---

## HTTP의 주요 특징

### 클라이언트-서버 구조 (Client-Server Architecture)

- **클라이언트**: 요청을 보내는 주체 (웹 브라우저, 앱 등)
- **서버**: 요청을 받아 처리하고 응답을 반환하는 주체

| 역할       | 설명                                    |
| ---------- | --------------------------------------- |
| 클라이언트 | 사용자 인터페이스와 사용자 경험 담당    |
| 서버       | 데이터 처리, 비즈니스 로직, 저장소 담당 |

> 이 구조 덕분에 클라이언트와 서버가 **독립적으로 발전**할 수있다.

### 무상태 구조 (Stateless)

HTTP는 **상태를 저장하지 않는(Stateless)** 프로토콜이다.

- 서버는 이전 요청에 대한 정보를 기억하지 않는다.
- 각 요청은 **완전히 독립적**으로 처리된다.

```
요청 1: "로그인" → 서버 처리 → 응답 반환 → 연결 종료
요청 2: "마이페이지" → 서버는 요청 1을 기억 못함
```

**장점**: 서버 확장이 쉽고, 서버 부담이 줄어든다.  
**단점**: 매 요청마다 인증 정보를 함께 보내야 한다.  
**해결책**: **쿠키(Cookie)**, **세션(Session)**, **JWT 토큰** 등을 활용한다.

---

## 주요 HTTP 메서드

| 메서드   | 의미             | CRUD   | 특징                           |
| -------- | ---------------- | ------ | ------------------------------ |
| `GET`    | 리소스 조회      | Read   | 데이터를 URL에 포함, Body 없음 |
| `POST`   | 리소스 생성      | Create | 데이터를 Body에 포함           |
| `PUT`    | 리소스 전체 수정 | Update | 전체 덮어쓰기                  |
| `DELETE` | 리소스 삭제      | Delete | 데이터 삭제                    |

### GET

```http
GET /users/1 HTTP/1.1
Host: api.example.com
```

- 서버에서 **데이터를 가져올 때** 사용
- URL에 파라미터를 포함할 수 있다: `/search?keyword=http`
- 여러번 호출해도 결과가 동일하다

### POST

```http
POST /users HTTP/1.1
Host: api.example.com
Content-Type: application/json

{
  "name": "김땡땡",
  "email": "hong@example.com"
}
```

- 새로운 **데이터를 생성할 때** 사용
- 데이터를 Body에 담아 전송한다
- 같은 요청을 반복하면 중복 생성될 수 있다

### PUT

```http
PUT /users/1 HTTP/1.1
Host: api.example.com
Content-Type: application/json

{
  "name": "김땡땡",
  "email": "new@example.com"
}
```

- 기존 **데이터를 전체 수정할 때** 사용
- 보내지 않은 필드는 null 또는 기본값으로 대체된다

> **PATCH**는 PUT과 달리 **일부 필드만** 수정할 때 사용한다.

### DELETE

```http
DELETE /users/1 HTTP/1.1
Host: api.example.com
```

- 특정 **리소스를 삭제할 때** 사용

---

## HTTP 상태 코드 (Status Code)

서버가 클라이언트의 요청에 대한 **처리 결과**를 3자리숫자로 알려준다.

### 상태 코드 분류

| 분류 | 범위    | 의미                          |
| ---- | ------- | ----------------------------- |
| 1xx  | 100~199 | 정보 응답 (처리 중)           |
| 2xx  | 200~299 | 성공                          |
| 3xx  | 300~399 | 리다이렉션 (다른 곳으로 이동) |
| 4xx  | 400~499 | 클라이언트 오류               |
| 5xx  | 500~599 | 서버 오류                     |

### 주요 상태 코드

| 코드  | 이름                  | 설명                                      |
| ----- | --------------------- | ----------------------------------------- |
| `200` | OK                    | 요청 성공                                 |
| `201` | Created               | 리소스 생성 성공 (POST 후)                |
| `204` | No Content            | 성공했지만 반환할 데이터 없음 (DELETE 후) |
| `301` | Moved Permanently     | URL이 영구적으로 변경됨                   |
| `302` | Found                 | URL이 임시로 변경됨                       |
| `400` | Bad Request           | 잘못된 요청 (문법 오류 등)                |
| `401` | Unauthorized          | 인증이 필요함 (로그인 필요)               |
| `403` | Forbidden             | 권한 없음 (접근 금지)                     |
| `404` | Not Found             | 요청한 리소스가 존재하지 않음             |
| `500` | Internal Server Error | 서버 내부 오류                            |
| `502` | Bad Gateway           | 게이트웨이/프록시 오류                    |
| `503` | Service Unavailable   | 서버가 일시적으로 사용 불가               |

---

## HTTP 통신의 메커니즘: 요청(Request)과 응답(Response)

HTTP(HyperText Transfer Protocol)는 클라이언트와 서버가 데이터를 주고받기 위한 **무상태성(Stateless)** 규약. 모든 통신은 구조화된 메시지를 통해 이루어진다.

[Image of HTTP request and response message structure]

### HTTP 요청 (Request) 구조

클라이언트가 서버에 특정 동작을 요구하는 메세지.

- **시작줄 (Start Line)**: `메서드(Method) + 경로(Path) + HTTP 버전`
  - 예: `POST /api/v1/login HTTP/1.1`
- **헤더 (Headers)**: 요청에 대한 메타데이터 (Host, User-Agent, Authorization 등)
- **빈 줄 (Empty Line)**: 헤더와 본문을 구분하는 필수 공백
- **본문 (Body)**: 서버로 보낼 실제 데이터 (주로 JSON 포맷)

---

### HTTP 응답 (Response) 구조

서버가 클라이언트의 요청을 처리한 결과를 전달하는 메세지.

- **상태 라인 (Status Line)**: `HTTP 버전 + 상태 코드(Status Code) + 상태 메시지`
  - 예: `HTTP/1.1 200 OK`
- **헤더 (Headers)**: 응답에 대한 부가 정보 (Content-Type, Cache-Control 등)
- **빈 줄 (Empty Line)**: 구분자
- **본문 (Body)**: 클라이언트가 요청한 데이터 (HTML, JSON, 이미지 파일 등)

---

### 상태 코드(Status Code)의 전략적 분류

서버는 상태 코드를 통해 요청의 처리 결과를 명확히 전달한다. 이는 프론트엔드에서 에러 핸들링을 수행하는 핵심 근거가 된다.

| 분류                    | 의미                | 대표 사례                                          |
| :---------------------- | :------------------ | :------------------------------------------------- |
| **1xx (Informational)** | 요청 수신 중        | 101 Switching Protocols                            |
| **2xx (Successful)**    | **요청 처리 성공**  | 200 OK, 201 Created (리소스 생성)                  |
| **3xx (Redirection)**   | **추가 동작 필요**  | 301 Moved Permanently, 304 Not Modified            |
| **4xx (Client Error)**  | **클라이언트 오류** | 400 Bad Request, 401 Unauthorized, 404 Not Found   |
| **5xx (Server Error)**  | **서버 내부 오류**  | 500 Internal Server Error, 503 Service Unavailable |

---

### Header의 역할ㅣ 통신의 제어와 최적화

헤더는 **메타데이터(부가 정보)**를 전달하며 `Key: Value` 형태로 작성. 단순히 정보를 전달하는 것을 넘어 캐싱, 보안, 데이터 형식을 제어.

**주요 요청 헤더 (Request Headers)**

- `Host`: 요청을 보내는 서버의 도메인 이름
- `Authorization`: 인증 토큰(JWT 등)을 담아 권한을 증명
- `Content-Type`: 보내는 데이터의 형식 (예: `application/json`)
- `Accept`: 서버로부터 받고자 하는 데이터 형식 설정

**주요 응답 헤더 (Response Headers)**

- `Set-Cookie`: 서버가 클라이언트에 쿠키를 저장하도록 지시
- `Cache-Control`: 브라우저가 응답 데이터를 얼마나 캐싱할지 제어 (성능 최적화의 핵심)
- `Access-Control-Allow-Origin`: CORS 정책 허용 여부를 명시

---

### Body의 역할: 실질적 가치 전달

Body는 **페이로드(Payload)**, 즉 실제 전송할 데이터를 담는 영역.

- **데이터의 유무**: `GET`, `DELETE`는 리소스의 식별에 집중하므로 Body를 생략하는 것이 관례이며, `POST`, `PUT`, `PATCH`는 리소스를 생성하거나 수정할 데이터를 Body에 포함.
- **형식의 다양성**: 응답 Body에는 단순 텍스트뿐만 아니라 JSON, 바이너리 데이터(이미지, 비디오), HTML 문서 등이 포함될 수 있으며, 이는 응답 헤더의 `Content-Type`에 의해 정의된다.

```json
{
  "status": 200,
  "message": "User information retrieved successfully",
  "data": {
    "uuid": "a1b2c3d4",
    "username": "developer_kim",
    "role": "admin"
  }
}
```
