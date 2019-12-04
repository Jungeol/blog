---
title: seminar-devfest2018.02
tag: seminar
category: seminar
date: 2019-12-04 21:40:29
---
# 실전 SPA상태관리 톺아보기
김동우
## SPA
- 승자는 React?
- React가 Vue보다 수익이 높은 편
## State Management가 필요
- React: Redux, MobX
- Vue: 전용이 있으나 위도 사용 가능
## Redux
- 다양한 환경
- 테스트하기 쉬움
- sate관리하기 위한 거대한 이벤트 루프
## 미들웨어
- redux-thunk: 비동기를 위한
- redux-saga: 사이드 이펙트를 이용한 데이터가 강점인 미들웨어
- redux-observable:
## redux-thunk
- 쉽지만 나쁘게 코딩하기 쉬움
- 테스트 디버깅 어려움
- 스파게티 코드가 되기 쉬움
- 발표자는 추천하지 않음
## Redux-saga
- 사이트 이펙트를 사용한 Data ochestration 미들웨어
- 중앙에서 액션을 보고있다가 사이드이펙트를 발생시켜 데이터 제어 시작
- 비동기를 동기 코드 처럼
- 테스트하기 좋음
- 복잡한 데이터 처리에 좋음
- ES6 제네레이터를 사용
- 장점
    - 일관된 비동기 처리제어로 앱의 데이터 흐름이 견고
    - 여러가지 작업을 처리하기 수월
- 단점
    - 배우는 과정이 고난
    - 액션을 작성하는데 더 많은 코드가 필요
## React Context API
- 리액트에 최근(16.3) 추가된 Context를 쉽게 생성할 수 있는 API
- Redux 없이도 간단하게 State Management 가능
- 장점
    - 간단하게 적용이 가능(Redux 안써도 됨)
- 단점
    - 스토어가 쉽게 비대해지는데 분리가 어렵
    - 항상 모든 컴포넌트가 다시 랜더링 됨(성능-)
## Mobx
- Simple, scalble state management
- functional reactive programming
- 개념적으로 어플리케이션 = 스프레드시트
- 학습비용이 낮음
- 장점
    - 코드가 간단해서 이해하기 쉽고 생산성이 좋음
    - 비동기 액션을 만들기 쉬움
- 단점
    - 디버깅하기 어려움
    - React 라이프사이클과 혼합하여 사용하기 어려움(mobex만 사용하는게 좋음)
## Redux vs mobx
- Redux가 압승
## MobX-state-tree
- model Driven State Management
- 복잡한 데이터를 다루는 앱에 적합
    - vs code 동시 코딩하는 기능
- 장점
    - 관계가 복잡한 데이터를 다루는데 수월
    - 견구하고 버그가 저근 개발이 가능(with typescript)
- 단점
    - 모델 작성하는 것이 학습비용도 크고 까다로움
    - 이렇게깢 견고해야하나 고민하게됨
## 결론
- Redux
    -가장 일반적인 경우
    - saga를 추천
- comtxt api
    - 간단한 앱에 적합
    - 추가합습비용0
- mobx
    - 높은 생산성 제공
    - 
## 적정 엔지니어링을 고려
- 오버엔지니어링을 경계해야함
- 해결 문제, 팀의 현재 수수준, 사용할 수 있는 자원
- Redux와 Mobx는 완전히 코드가 상이

## Bonus
- React state museum
    - 여러가지 스테이트로 같은 어플 개발
    - 샌드박스로 바로 확인 가능

## 주식회사 체커