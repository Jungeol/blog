---
title: seminar-devfest2018.03
tag: seminar
category: seminar
date: 2019-12-04 21:40:29
---
# PWA
## 로딩시간
- tti: 5초 이하
- 나머지 로드: 2초 이하
## SPA
- 장점이 많지만 초기구동속도가 느림
## 퍼포먼스
- 자바스크립트 170kb
- jpg 170kb
- 두가지는 많은 차이가있음
## tti 줄이기
- 배포과정을 최적화
    - PRPL Pattern: 웹앱을 배포할때 ux를 최적화하는것
        - PWA로 만듬
## PRPL 패턴
- 완벽하게 맞추기엔 생태계가 덜 발전함
## Dinamic Code splitting + lazy loading
- Route-based bundle
- React-Loadable 라이브러리
    - pre-loading
- Minfy + Compress
    -Minify: webpack, uglify
    -compress: gzip
## Chrome Aduit
- 로드 퍼포먼스 체크
## Server Side Rendering
- Isomorphic(Universial) Web App
## Next.js

## PWA
- Workbox: 구글에서 발표한 PWA용 라이브러리
## 최적화
- 웹팩 관련이 50% 이상