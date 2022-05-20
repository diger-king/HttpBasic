# URI 와 웹 브라우저 요청 흐름

---

## URI

Uniform Resource Identifier

리소스를 식별하는 통합된 방법

---

### Uniform : 리소스를 식별하는 통일된 방식

### Resource : URI 로 식별할 수 있는 모든 것(정말 모든 것 구분만 되면 됨)

### Identifier : 다른 항목과 구분하는데 필요한 정보

---

## URI vs URL vs URN

> URI 는 로케이터(locator), 이름(name) 또는 둘 다 추가로 분류될 수 있다.
>
> URI(Resource Identifier) = URL(Resource Locator) + URN(Resource Name)

### URL
리소스가 위치한 위치를 나타낸다. (ex) 디렉터리 경로)

-> https://example.com:8080/hi/there

### URN
리소스의 이름을 나타낸다. (ex) 파일 이름)

---

> URN 은 그 이름만으로 실제 리소스를 찾을 수 있는 방법이 보편화 되어있지 않다.
>
> URL .=. URI

---

## URL 분석

> https://www.google.com/search?q=hello&hl=ko
>
> scheme://userinfo@host:port/path?query#fragment

프로토콜 - https

호스트명 - www.google.com

포트번호 - 443

경로 - search

쿼리 파라미터 - q=hello&hl=ko

---

# 웹 브라우저 요청 흐름

0. https://www.google.com:443/search?q=hello 입력 시

1. DNS 조회 (DNS To IP)

2. PORT 체크

3. HTTP 요청 메시지 생성

---

## HTTP 요청 메시지 생김새

> GET /search?q=hello&hl=ko HTTP/1.1
> 
> Host : www.google.com

## HTTP 메시지 전송 과정

1. 웹 브라우저가 HTTP 메시지 생성

2. SOCKET 라이브러를 통해 전달
   1. TCP/IP 연결(IP, PORT)
   2. 데이터 전달

3. TCP/IP 패킷 생성, HTTP 메시지 포함

### 최종 패킷 형태

    [TCP/IP 패킷]
    출발지 IP + PORT
    목적지 IP + PORT

    +

    [HTTP 메시지]
    GET /search?q=hello&hl=ko HTTP/1.1
    
    Host : www.google.com

### 수신측에서 패킷을 받으면 어떻게 하나?

TCP/IP 패킷은 버리고 HTTP 메시지를 해석한다.

그 후 HTTP 응답 메시지를 보내준다.

