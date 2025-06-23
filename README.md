# FastAPI Learning

### 🔹 **FastAPI 개요**

- **FastAPI**는 **빠르고(FAST)**, **간단하며(EASY)**, **자동 문서화가 가능하고(DOCUMENTED)**, 
**비동기(ASYNC)** 프로그래밍을 지원하는 Python 웹 프레임워크입니다.
- Python 3.6+의 **타입 힌트(Type Hints)**를 적극 활용하여 **자동 검증 및 문서 생성**이 가능합니다.

---

### 🔹 **FastAPI의 주요 특징**

| 특징 | 설명 |
| --- | --- |
| ✅ 빠른 성능 | Starlette과 Pydantic 기반으로 매우 빠름 (Node.js, Go에 근접) |
| 🧠 자동 문서화 | Swagger UI, ReDoc 문서 자동 생성 (`/docs`, `/redoc`) |
| 🎯 타입 기반 설계 | Python 타입 힌트를 활용한 자동 요청/응답 검증 |
| 🔄 비동기 지원 | `async`/`await` 기반 비동기 처리로 높은 동시성 제공 |
| 📦 쉬운 연동 | 데이터베이스, OAuth2, JWT, 백그라운드 작업 등 다양한 기능 쉽게 통합 가능 |

```python
from fastapi import FastAPI

app = FastAPI()

@app.get("/")
def read_root():
    return {"message": "Hello FastAPI!"}

@app.get("/items/{item_id}")
def read_item(item_id: int, q: str = None):
    return {"item_id": item_id, "query": q}
```

- `@app.get("/")`: HTTP GET 요청을 받는 엔드포인트
- 타입 지정 (`item_id: int`)은 자동 검증 및 문서화에 사용됨

---

### 🔹 언제 사용하나요?

- RESTful API 서버 개발
- AI/ML 모델 서빙 (e.g. 모델 예측 결과 API 제공)
- 마이크로서비스 백엔드 구축
- 빠른 MVP나 프로토타입 개발

---

## ✨공부 방법

**기본 개념 → 실습 → 확장 → 프로젝트** 순으로 학습하기.

### 1단계: **기초 이해 및 환경 세팅 / 기초기능 구현**

🔸 **목표 :** FastAPI가 무엇인지 이해, 개발 환경 구성

- [x]  **Python 3.8+ 설치** [실습시엔 3.10 버전으로 사용함]
- [x]  **가상환경(venv)** 생성 [실습 개발환경은 **pycharm** 이용.]
- [x]  FastAPI & Uvicorn 설치 [Uviocorn은 실시간 미리보기 패키지]

![image.png](/Pic/image.png)

- [x]  [기초 기능 구현해보기](https://www.notion.so/FastAPI-Learning-1d17f052d951800bbc97dd9f21f158eb?pvs=21)(클릭시 코드로 이동)

### 2단계: **핵심 기능 익히기 (중요)**

**🔸 목표 :** FastAPI의 주요 개념을 익히고 예제로 직접 실습

- 라우팅 (GET, POST, PUT, DELETE)
- Path & Query Parameter
- 요청 바디 처리 (Pydantic 모델)
- 응답 모델(ResponseModel)
- 상태 코드 및 예외 처리
- Swagger UI & ReDoc 자동 문서화

---

### 3단계: **확장 기능 익히기**

- 비동기 처리 (`async def`)
- 데이터베이스 연동 (예: SQLite → PostgreSQL)
- ORM 연동 (예: SQLAlchemy, Tortoise ORM)
- JWT 기반 인증
- CORS, Middleware 설정

---

### 4단계: **실전 감각 익히기**

🔸 **목표 :** 간단한 기능을 실제 구현해보며 익히기

- TODO 리스트 API
- 메모장/일기장 REST API
- 간단한 로그인/회원가입 API (JWT 토큰 사용)
- 영화 정보 조회 API

---

### 5단계: **작은 프로젝트 만들기**

- 간단한 API를 직접 만들어보고 GitHub에 업로드

---

## 🎯 공부 팁

| 팁 | 설명 |
| --- | --- |
| 📘 공식 문서 | FastAPI 문서는 아주 친절하고 잘 되어 있음 |
| 💻 따라 해보기 | 코드 한 줄씩 따라치며 직접 실행해보기 |
| 🧠 개념 복습 | `GET/POST 차이`, `Path vs Query param`, `Pydantic` 구조 이해 |
| ❓ 궁금한 건 검색 | 에러가 나면 검색 → 해결 과정이 실력! |
| 📦 GitHub 기록 | 배우는 걸 정리하며 올리기 → 포트폴리오로도 사용 가능 |

---

# 🍎코딩애플님의 유튜브 영상

**유튜브 영상 : [느슨해진 백엔드씬에 긴장감을 주는 FastAPI 프레임워크](https://www.youtube.com/watch?v=5A67mQ2Pt9s&list=LL&index=4)**

파이썬으로 웹서버를 만들때 대부분 Django, Flask를 사용, 허나 요즘은 FastAPI를 사용하기도 함.

FastAPI의 장점은 위의 2가지 프레임워크보다 2배 빠르며 코드가 간결하고 쉽다.

- 벤치마크 성능 비교
    
    ![image.png](image%201.png)
    
    ![image.png](image%202.png)
    
    실제 벤치마크를 살펴봐도 DB입/출력, 서버의 응답속도가 2배정도 빨라 뛰어난 성능을 보임.
    
    그 이유는 **비동기처리**를 기본적으로 지원하는 프레임워크 이기 때문.
    

---

- 비동기처리(**Async/await)**란?
    
    [async/await 개념 정리](https://trustmitt.tistory.com/85)
    
    ![image.png](image%203.png)
    
    **프로그램이 특정작업을 동기적으로 처리하지 않고,** **해당 작업이 완료될 때 까지 기다리지 않고 다른 작업을 수행할 수 있는 프로그래밍 패러다임**
    
    특정 코드가 오래 걸리면 일단 제껴두고 다른 코드부터 실행이 가능한것.(ASGI 덕분에 비동기처리 가능)
    
    java script랑 동작방식이 유사하다.
    
    ### 비동기 처리 방식의 필요 이유
    
    1. **웹 페이지의 반응성 향상** : 사용자가 요청한 작업이 완료될 때까지 기다리는 것은 사용자 경험을 저해시킨다. 따라서, 비동기 처리를 통해 사용자의 요청에 빠르게 반응할 수 있도록 해야 한다.
    2. **네트워크 통신** : 웹 애플리케이션에서는 서버와의 데이터 통신이 필요하다. 동기적인 처리를 하게 되면 응답을 기다리는 동안 다른 작업을 수행할 수 없기 때문에 웹 페이지의 반응성이 떨어질 수 있다. 따라서, 비동기적으로 데이터를 받아오는 것이 웹 페이지의 성능을 향상시키는데 도움이 된다.
    3. **병렬 처리** : 비동기 처리를 통해 여러 작업을 동시에 처리할 수 있다. 이를 통해 시간이 오래 걸리는 작업을 병렬적으로 처리할 수 있으며, 결과적으로 전체 작업 시간을 단축시킨다.
    4. **에러 처리** : 비동기적으로 처리할 때 에러가 발생하면, 해당 에러를 쉽게 처리할 수 있다. 에러 발생 시, 에러를 처리할 수 있는 콜백 함수를 실행하거나, 에러를 캐치하여 처리할 수 있어 프로그램의 안정성을 높일 수 있다.
    
    출처: [kohigowild:티스토리]
    
    [https://trustmitt.tistory.com/85](https://trustmitt.tistory.com/85)
    

---

![image.png](image%204.png)

요청이 매우 많은 사이트를 만든다면 좋은 방법으로 볼수 있음

---

### FastAPI의 특별한 기능들

- GET/POST 요청받기
- DB 입/출력
- 회원인증
- 데이터 validation
- 웹소켓
- async/await
- type 넣기
- API 문서 자동생성

---

- FastAPI는 웹 개발 프레임워크라기 보다는 광범위한 API만드는 툴이라 본다.

![image.png](image%205.png)

요즘은 서버 개발을 할때 django처럼 크게 개발하는것 보다. MSA(**Micro Service Architecture)방식**

즉, FastAPI는 복잡한 애플리케이션(서버)을 작은 독립적인 서비스 단위로 나누어 개발하는 방식으로 사용함.

---

### **간단한 웹서버 만들어보기**[기초 기능 구현]

- 실습 내용
    - 메인페이지 접속시 **`FastAPI 메인페이지 연습입니다.`(데이터)**가 보이도록 연습해보기
    
    ```python
    from fastapi import FastAPI
    app = FastAPI()
    
    @app.get("/")
    def Main():
        return 'FastAPI 메인페이지 연습입니다.'
    ```
    
    ![image.png](image%206.png)
    
    - /data (경로)로 접속시 다른 데이터가 보이도록 연습해보기
    
    ```python
    from fastapi import FastAPI
    app = FastAPI()
    
    @app.get("/") #첫 페이지 화면
    def Main():
        return 'FastAPI 메인페이지 연습입니다.' #페이지에 나타낼 구문을 작성
    
    @app.get("/data")
    def Sub():
        return {'안녕하세요' : 1234} #딕셔너리 자료 형태로 표현해봄.
    ```
    
    ![image.png](image%207.png)
    
    - /docs 로 접속시 웹서버를 만들며 사용한 기능들을 API문서형태로 정리해줌
    
    ![image.png](image%208.png)
    
    ![경로를 /redoc으로 치면 다른 형태로도 볼 수있다.](image%209.png)
    
    경로를 /redoc으로 치면 다른 형태로도 볼 수있다.
    
    - 내가 만약 메인페이지 접속시 html 페이지를 전송하고 싶다면 다음 코드를 import 해준다.
    그리고 파일을 보낼 경로를 적기 위해 FileResponse( ) 함수를 이용한다.
    
    ```python
    from fastapi.responses import FileResponse
    
    return FileResponse('파일명')
    ```
    
    - 결과적으로 내가 index.html이라는 파일을 전송하여 메인페이지에서 보여주고 싶다면 다음과 같이 진행해야한다.
    
    ![      index.html 파일생성](image%2010.png)
    
          index.html 파일생성
    
    ```python
    from fastapi import FastAPI
    app = FastAPI()
    
    from fastapi.responses import FileResponse
    
    @app.get("/")
    def Main():
        return FileResponse('index.html')
    ```
    
    ![image.png](image%2011.png)
    
    - 이번에는 유저에게 데이터를 받는 경우이다. 
    유저들이 이름, 연락처를 서버에 보내고 싶어할때 수신하는 기능은 다음과 같다.
    
    ```python
    from pydantic import BaseModel #유저에게 데이터를 받으려면 모델이 필요하다.
    
    class Model(BaseModel): #모델 만들시 (BaseModel)을 작성해야함.
        name : str #이름 데이터[string 타입]
        phone : int #연락처 데이터[int 타입]
    
    @app.get("/send") #유저들은 /send라는 url로 데이터 2개[name, phone]를 보내고
    def Send(data : Model): #보낸 데이터는 data에 담긴다. (참고로 함수나 변수에 타입기능 기본제공)
        print(data) #담긴 데이터 볼 수 있음.
        return '전송완료'
    ```
    
    ---
    
    - 또 DB를 접속하고, 데이터를 꺼내오는 기능도 존재하며, async/await 키워드로 비동기처리 기능 사용가능

---

# **📖[점프 투 FastAPI](https://wikidocs.net/book/8531)**

"점프 투 FastAPI"는 "파이보"라는 이름의 파이썬 게시판(Python Board) 서비스를 만들어가는 과정을 설명한 FastAPI 입문서이다. 파이썬 설치부터 시작하여 서비스 운영까지 웹 프로그래밍의 처음부터 끝까지 모든 것을 알 수 있도록 구성하였다.

- **이 책을 이해하기 위해 필요한 사전지식**
    
    이 책을 읽고 이해하기 위해서는 다음과 같은 사전 지식이 필요하다.
    
    - **파이썬 기초 지식** - [<점프 투 파이썬>](https://wikidocs.net/book/1) 책 정도의 내용을 이해할 수 있다면 OK
    - **HTML 기초 지식** - `<table>`, `<div>`, `<form>` 태그가 무엇인지 알고 있다면 OK
    - **CSS 기초 지식** - 스타일시트 파일을 작성해 본 적이 있다면 OK
    - **자바스크립트 기초 지식** - 자바스크립트를 작성해 본 적이 있다면 OK
    - **폼(form)에 대한 지식** - 브라우저가 서버에 요청을 보낼 때 사용하는 GET, POST 방식의 차이점에 대해 알고 있다면 OK
    - **데이터베이스에 대한 기초 지식** - 테이블이 무엇인지 SQL 쿼리가 무엇을 의미하는지 알고 있다면 OK

## 📅 1–2주차: 환경 설정과 '안녕하세요, 파이보' 만들기

- 교재 **1장** 중심 학습
    - [x]  파이썬 및 FastAPI 설치, 개발 환경 구성 (PyCharm, 가상환경 등)
    - [x]  간단한 FastAPI 서버 생성 및 “안녕하세요 파이보” 출력 (`@app.get("/hello")`)
    - [x]  Svelte 개발 환경 준비 및 연동 실습
    - [x]  Swagger UI, Redoc 문서 자동 생성 체험
- **연습**: 다양한 엔드포인트 만들어보고, 경로 매개변수, 쿼리매개변수 사용해 보기

[1~2주차 Study Note](https://www.notion.so/1-2-Study-Note-2127f052d9518054a0e0cdeff57b04a2?pvs=21)

---

## 3–4주차: FastAPI 기초 및 DB 모델링

- **2‑01 ~ 2‑03장**
    - [x]  SQLAlchemy 기반 데이터베이스 연결, `Base`, `SessionLocal`, `get_db()` 등 구성
    - [x]  DB 테이블, 모델 생성 및 CRUD 메서드 실습
- **연습**: CRUD 테스트 API 구현 및 Uvicorn 서버에서 확인

[***3~4주차 Study Note***](https://www.notion.so/3-4-Study-Note-2127f052d95180169d8bd0d978b9bc85?pvs=21)

---

## 5–6주차: 게시판 ‘질문’ 엔티티 완성

- **2‑04 ~ 2‑10장**
    - [x]  라우터(Router), 의존성 주입(Dependency Injection), Pydantic 스키마
    - [ ]  질문 목록 API, 질문 상세 API 구현
    - [ ]  API 호출을 위한 Svelte 프론트엔드 구성
    - [ ]  답변 등록, 질문 등록 기능 완성
    - [ ]  화면 UI 개선: Bootstrap 적용, CSS 조정
- **연습**: CRUD UI 완성, 테스트 데이터로 기능 점검

[5~6주차 Study Note](https://www.notion.so/5-6-Study-Note-2127f052d95180239e4bf52e67c0ea04?pvs=21)

---

## 7–9주차: 파이보 게시판 서비스 고도화

- **3장(3‑01 ~ 3‑16)**
    - [ ]  네비게이션 바, 게시판 페이징, 날짜 포맷, 일련번호, 답변 수 표시
    - [ ]  회원가입·로그인·로그아웃 ·세션 관리
    - [ ]  글쓴이 정보 저장·표시, 게시글 수정/삭제, 추천, 마크다운 렌더링, 검색 기능 구현
    - [ ]  프론트엔드 빌드 및 실무 기능 추가
- **연습**: 인증 흐름 점검, 검색·추천 성능 테스트

---

## 10–12주차: 배포 & 운영

- **4장(4‑01 ~ 4‑14)**
    - [ ]  Git/GitHub로 버전 관리
    - [ ]  서버 환경 이해: AWS LightSail 활용
    - [ ]  Gunicorn, Nginx 설정 및 UNIX 소켓 기반 서비스
    - [ ]  로깅, 도메인, SSL(Secure Sockets Layer), PostgreSQL 적용
- **연습**: AWS에서 실 서비스 배포, HTTPS 접속점검

---

## 🎁 부록 & 고급 주제 (옵션)

- **A‑01**: 비동기(async) 기반의 질문 목록 조회
- **A‑02**: AWS LightSail 취소 및 대체 클라우드 리소스 구성
- **연습**: `async def`, `await` 적용 테스트, 다른 클라우드 환경 연습

---

## ✅ 커리큘럼 요약표

| 주차 | 주요 학습 내용 |
| --- | --- |
| 1–2주 | 환경설정, FastAPI 기초, Hello API, Swagger 문서 |
| 3–4주 | DB 구성, 모델 및 CRUD, Pydantic 스키마 |
| 5–6주 | 질문 게시판 기능, 프론트엔드 연동, UI 구현 |
| 7–9주 | 회원 기능, 추천/검색/Markdown, 페이지 빌드 |
| 10–12주 | Git, AWS 배포, Gunicorn/Nginx, 로깅, 도메인, SSL, PostgreSQL |
| 추가 | 비동기 API, 클라우드 실험 |

---

## 💡 학습 팁

- **GitHub 활용**: 챕터별 branch 나누기, 커밋 기록 체계관리
- **협업 연습**: 최소 한 번은 팀원과 코드 리뷰 및 기능 분업 경험
- **테스트 작성**: `TestClient`, `pytest`로 API 엔드포인트 자동화 테스트
- **확장 프로젝트**: 채팅, 알림, 파일 업로드, Docker Compose 적용 등 추가 연습

# [BIPA SORI님의 파이썬 FastAPI학습](https://www.youtube.com/playlist?list=PLr_ki3_GfpZMTSdQehJRrIwuDGOHh5LvB)

## FastAPI 기초 - GET, POST, DELETE

---
