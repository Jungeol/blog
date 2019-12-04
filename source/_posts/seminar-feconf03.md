---
title: seminar-feconf03
tag: seminar
category: seminar
date: 2019-12-04 21:40:29
---
# ReactComponent와 D3 Object를 유기적으로 연결하는 전략
박승현 eldeniyenden@gmail
eldeni.github.io
## SVG
- 캔바스보다 느림
- 다루기 쉽고 확대해도 잘보임
## chart 라이브러리
- chart.js
- c3.js
- rechars.js: 확장이 어려움
- *d3.js: dom레벨, 큰 커뮤니티
## 언제 선택을 하는가
- 데이터 시각화를 하고싶은데 특별하게 할때
- 리액트나 앵귤러같은 제3에 기대지 않는것
- dom조작을 해봤다면 더 좋음
## 리액트 Webapp에 d3를 바인딩
- 돔조작 컨플릭트가 남
- 리액트 상태관리시 계속 로드되면서 퍼포먼스 저하가 발생함
## 두가지 해결방법
1. 리액트가 전부다 관할을 하게
    -D3는 수학적 계산만함
2. 각각의 파트를 관리하는 방법
    - 리액트는 div까지만 랜더링
    - D3는 수학계산과 dom조작 까지
## 선택한벙법
2번으로 선택함
1. 디버깅하기 쉬웠고
2. 리액트없이 사용가능
3. d3샘플이 많다
## dechart.js -> github
## 요약
- 둘다 돔을 다루지만 같이 다룰수 있다
- 가능하다면 분리해야한다
## 끝
eldeni.github.io