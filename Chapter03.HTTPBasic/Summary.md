# HTTP 기본

---

## HTTP 메시지에 무엇이 담길 수 있나?

- HTML, TEXT

- 이미지, 음성, 영상, 파일

- JSON, XML (API)

- 서버 간 데이터를 주고 받을 때도 대부분 HTTP 사용

---

## HTTP 역사

#### HTTP/0.9 1991년 : GET 메서드만 지원, HTTP 지원 X

####  HTTP/1.0 1996년 : 메서드, 헤더 추가

####  HTTP/1.1 1997년 : 가장 많이 사용 (RFC2068 -> RFC2616 -> RFC7230 ~ 7235)

####  HTTP/2 2015년 : 성능 개선

####  HTTP/3 진행 중 : TCP 대신 UDP 사용, 성능 개선 

---

## 기반 프로토콜

TCP : HTTP/1.1, HTTP/2

UDP : HTTP/3

TCP 는 3-way handshake 과정으로 인해 속도가 느릴 수 밖에 없다.

---

