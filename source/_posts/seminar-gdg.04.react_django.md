---
title: seminar-gdg.04.react_django
tag: seminar
category: seminar
date: 2019-12-04 21:40:29
---
# React와 Django로 만드는 Progressive WebApp.
진유림, 핑크퐁
## Prograssive Web App
1. 프로그레시브
2. 반응형 지원
3. 설치가능&웹과 유사
4. 따로 업데이트를 할 필요가 없음
### Service Worker
- 브라우저와 서버 사이의 미들웨어
- Cashe-First Strategy
- 서비스워커를 브라우저에 등록하기
    - create-react-app
- sw-precach
- 홈 화면에 추가해서 앱처럼 쓰기
    - menifest.json 파일 작성
### 브라우저
- 사파리 지원안함
## Web Push
- firebase cloud messaging
- 파이어베이스를 통해서 편하게 푸쉬 메세지를 보내고 받을 수 있음
- foreground, background 따로 구현해야함
- 파이썬: Pyfcm
- 모바일은 홈화면에 추가했을때, pc는 브라우저가 켜져있을때
### pwa 후기
1. 먼저 pwa를 적용을 꼭해야하는지 생각
2. 서비스워커의 구조 이해
3. 토이프로젝트, 사내서비스에 선 적용해보기
### https://github.com/milooy/react-django-pwa-kit
