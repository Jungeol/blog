---
title: seminar-masocon2017
tag: seminar
category: seminar
date: 2019-12-04 21:40:29
---
# 우아한 오픈소스
우아한형제들 김민태 수석
## WoowahanJS
- 퍼블리셔와 프론트엔드 개발자의 협업
### B2C web App
잦은 UI 업데이트
복잡하고 디테일한 UI 구성
트랜드에 민감함 UX
재사용률 1.5%
### Backoffice Web App
단순한 CRUD 구조
재사용률 높은 UI
촉박한 개발 일정
쉽게 확장되는 스케일
### 웹 앱은 무엇을 하는가?
Template string + Data => HTML + CSS
### gitbook-markdown
## 릴리즈 관리
서비스 개발과 근본적으로 다르다
-> 오픈소스를 개발하면서 버전관리의 기틀마련
# 오픈소스를 활용한 AI기반 검색 서비스 구축기
버즈니 남상협 대표
## 검색엔진
1. 어떤 엔진을 쓸것인가
Lucene
Elasticsearch
Solar
2. 검색의 기본 1 - 언어처리(Segmentation)
- 검색어를 의미 단위로 잘 나누는것이 기본중의 기본.
- 설정하지 않을 경우, bigram으로 쪼개게 됨.
-> 도메인 specipic하기 때문에 자체적으로 언어처리 오픈소스를 만들게됨
- 자체적으로 학습 데이터를 만든후 CRF++라는 오픈소스 활용 ->  BiLSTM-CRF 기법
3. 검색의 기본 2 - 성능평가
- 취지
    - 성능의 기준접 필요
    - 검색 랭킹에 사용되는 요소들의 가중치 기준점도 필요
- 만드는 방법
    - 특정 query에 대해 나오는 검색 결과에 대해서 high relevant, relevant, non relecant, pam 등으로 표시해서 만듬
    - Normalized Discounted Cumulative Gain 기법으로 평가
4. 검색 + AI, 카테고리 분류기
- 카테고리 분류 문제, ex> 노트북 -> 노트북 받침대 나옴
- Query의 카테고리와 상품의 카테고리를 비교해야 문제 해결 가능
- 개발 툴 : Jupyter Notebook 개발하는데 활용
- 머신러닝 : Sscikit-Learn의 SVM 모델로 학습, 현재는 Torch를 사용하여 딥러닝 피쳐가지 활용
-> 1억개 상품에 대해서 수천개의 카테고리로 자동으로 분류
5. 검색 + AI, Learning To Rank
- query와 상품간의 카테고리 매치 점수를 비롯한 다양한 랭킹요소 -> Elasticsearch의 Function_score기능
-> Learning to rank
6. 검색 + AI - 이미지 인식 검색 기술 개발
- 이미지에서 Feature추출: torch의 cnn모델 사용
- 이미지에서 특정 객체 인식: Faster RCNN
- 상품 정보 검색: Elasticsearch
-> 샷핑이라는 서비스 출시함
## 오픈소스들을 잘 활용하려면?
- 깃허브 트렌딩 주기적으로 살펴보기
- 명확한 니즈가 있을때 사용하고, 실제 서비스 적용하기
- 사용하려는 분야에 대한 꾸준한 학습
- 피룡하면 오픈소스 코드 내부를 보고 고쳐서 사용할 정도의 실력 키우기
## 라이트닝 토크()
1. 한글로하는 일본어 입력
2. 아시아 우분투 컨퍼런스
    - Snap, Flatpak, AppImage
3. 오픈스택 커뮤니티
    - 프로그래머블 인프라
4. 추억의 자바스크립트
## React.js에 반응하라
김동우(gimdongwoo@gmail.com)
자바스크립트 개발자 포럼
### Angular.js vs React.js
### 리액트 특징
1. Vertual DOM
    - 리랜더링이 일어날때 diff만 계산해서 다시그림
2. Data flow
    - 단방향
    - 주어딘 데이터가 같으면 같게 그려짐
    - 추적하기 쉬움
3. JSX
    - XML 문법을 JS 코드에서 사용
    - html 같아 보이지만 아님
4. Declarative
    - 선언적 뷰는 코드를 예측하기 쉽게 만들어줌
5. Component
    - 재사용 가능한 UI 덩어리
    - Lifecycle
    - 데이터를 property로 부모로부터 주입
6. Lifecycle
7. React는 Component tree
8. 선언적 뷰 렌더링이 주는 편안함
## React Native
1. 네이티브 앱
2. 80%의 코드가 js로 ios/android 공유됨
## 필요한것
1. Redux
    - JS 앱을 위한 예측가능한 상태 컨테이너
    - 미들웨어
2. ReactRouter
    - 브라우저로부터 url을 라우팅 하는것->뷰를 골라줌
    - 서버사이드 랜더링을 위한 필수요소
3. nodejs + Express
    - React 번들을 provide하기에 제일 적합함
    - React-hot-loader를 사용해서 효율성
4. webpack
    - javascript번들링 툴
    - webpack-dev-server
5. Babel
    -ES6 + JS 문법을 브라우저 지원에 맞게 트랜스 코딩
    -webpack의 barbel-loader 호출
6. 간편하게
    -무작정 시작하기 : create-react-app
    -간편하게 SSR : Next.js
## 부록
1. 해서 안되는것
    - Random value
        - Render가 일어날때마다 값이 바뀌는 패턴을 만들면 망
        - math.random(), new Date() 쓸때 주의
    - Uncontrolled input
## 질문 : React - ReactNative 간 코드 공유가 되나
1. 비즈니스로직은 공유가 되나.
2. React - ReactNative 간의 코드 공유는 불가
# Electron, Typescript, 성공적
서울JS 이웅재 운영진
## 일렉트론
- 데스크탑 어플리케이션을 만드는 용도
- HTML/CSS/JavaScript ui -> chromium ui 라이브러리 기반
- JavaScript로 OS와 연결된 Electron Api
- Node.js 완전히 사용 가능
- Node.js npm 모듈 사용가능
## 일렉트론을 쓴것
- Now 데스크탑, 깃헙 데스크탑, 하이퍼 cmd
## 장점
- 프로젝트가 빠르게 성장
- 서드파티 커뮤니티: Electron Userland
- 검증되있고, 상용을 위한 준비가 잘 되어있음
    - 자동업데이트, 설치, 배포 관련
    - VS Code가 표준
## 단점
- 기본 실행파일이 100M
- 리소스를 많이 먹음
- 윈도우에서의 사용이 상대적으로 불안정
- 소스보호를 공식적으로 제공하지 않음
    - 소스를 다 볼 수 있음
## Proto pie에서 도입한 이유
- 웹개발자가 접근하기 쉬움
- 많은 UI 레퍼런스가 있음
- 크로스 플랫폼
- 좋은 퀼의 앱을 빠른시간에 런칭
- ES6를 자연스레 사용
- es7 async-await
## TypeScript 도입
javascript 컴파일 언어
1. javascript에 없는 스팩을 손쉽게 사용 가능
2. 타입 시스템이 가장 핵심
커맨드 패턴 적용 해서 쓰고있음
# R로만드는 API서버 삽질기
박찬엽
# 협업으로 달라붙고, 빌드 자동화로 편해지자.
배준현 코무합니다만
## 협업툴
- 아틀라시안, 트렐로
## 소스관리툴
- 깃랩
## 빌드 master 브랜치 트리거
- Travis CI -> github에 붙여쓸수있는
- 젠킨스
# 오픈소스 라이선스와 컴플라이언스
한국공개소프트웨어협회
박준석 수석, dkaien77@hanmail.net
## 오픈 소스 소프트웨어 라이선스
소스코드를 개방했을 뿐이지, 저작권으로 보호 받고 있음
GPL: 상업적으로 이용어려움
### 분류
1. Permissive
    - 제한없음
2. Weak Copyleft
    - 약한제한
3. Strong Copyleft
    - 강한제한
-> 대부분의 오픈소스는 배포시에 의무가 적용
### 조심
- GPL
    - GPL 전염
    - 코드 수정없이, 다른 프로세스로 사용하면 적용이 안됨
    - 소스코드 받아서 재배포 가능
- LGPL
    - StaticLink: Object Code 제공, Dynamic Link: 제공필요없음
    - 소스코드 공개 의무 전혀 없음
- AGPL
    - 통신을 해도 통신을 하는 사용자에게 소스 코드 공개 필요
    - 공개의무가 없는 라이선스로 선언된 드라이버 있으면 필요 없음
- MPL
    - 복사하거나 복사해서 수정한 코드만 공개
- EPL
    - 모듈단위 공개의무
### 양립성
- 라이선스끼리 같이 사용못하는 경우도 있음
- 하이브리드 라이선스
### 버전변경
- 업데이트를 하면 라이센스 변경 가능
### 특허이슈
- 특허 무료 사용 권한 허용
## 오픈소스 라이선스 컴플라이언스
- 제품 정책 결정
- 오픈소스 적합성 검토
- 취약점 검토
- 양림성 검토
-> 파솔로지, 오픈소스 라이센스 검토
# 개울가의 올챙이 한마리, 꼬물 꼬물 헤엄치다.
테드폴허브 조현종 대표
평펌한 개발자 오픈소스로 먹고살기 v0.3
## 오픈소스 올챙이
- 엔터프라이즈를 팔아서 수익
## 오픈소스로 먹고사는 방법
- 오픈소스 회사에 입사해서 개발
- 입사해서 오픈소스 개발
- 오픈소스를 만들어서 후원/창업
## TOAD vs 올챙이
# 데이터 정의로 밝힌 내 삶의 햇볕
카카오뱅크 성동찬 DBA
## Backup
1. 복구, 소산 등
2. 백업대상의 IDC가 변경될 수 있다
## MHA + LOSRESS REPLICATION