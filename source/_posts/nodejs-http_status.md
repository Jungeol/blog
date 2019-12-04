---
title: nodejs-http_status
tag: nodejs
category: nodejs
date: 2019-12-04 21:40:29
---
# HTTP Status
## 요약
- 1xx: 끊지 마, 아직 처리중이야.
- 2xx: 자, 여기 있어!
- 3xx: 잘 가~
- 4xx: 네게 문제가 있음
- 5xx: 내게 문제가 있음
## 자세히
1. 100 범위
    - 100: 계속
    - 101: 프로토콜 전환
2. 200 범위
    - 200: 성공(OK)
    - 201: 작성됨(CREATED)
    - 202: 허용됨(ACCEPTED)
    - 204: 콘텐츠 없음(NO CONTENT)
3. 300 범위
    - 301: 영구적으로 이동됨(MOVED PERMANENBTLY)
    - 303: 기타 위치 확인(SEE OTHER)
    - 307: 임시 리디렉션(TEMPORARY REDIRECT)
4. 400 범위
    - 401: 권한없음(UNAUTHORIZED)
    - 403: 금지됨(FORBIDDEN ERRORS)
    - 404: 찾을 수 없음(NOT FOUND)
5. 500 범위
    - 500: 내부 서버 오류(SERVER ERROR)