---
title: seminar-gdg.05.jamstack
tag: seminar
category: seminar
date: 2019-12-04 21:40:29
---
# JAMstack이 Giihub와 CloudeFlare를 만날때 고성능 웹 어플리케이션 호스팅은 무료가 된다.
By Byungjin Park
How it feels to learn javascript in 2016?
## JAM STACK
###모던앱을 위한 스택
Javascript: 
API: 
Markup: 배포시 빌드 가능한 마크업 템플릿 엔진 사용(깃북, 지킬, 휴고, 헥소, 웹팩)
### StaticGen
스태틱사이트 제네레이터 비교 사이트
### Profits
좋은 퍼포먼스
운영 웹서버 불필요, 정적파일 호스팅만 필요
CDN을 활용한 높은 보안
Better Developer Experience
### Best Practices
1. 모든 프로젝트는 CDN에 업로드
2. 배포시 CDN 즉시 폐기
3. 배포는 모든 변경파일이 업로드 완료시에 적용
4. git으로 버전관리를 하고 단일 표준 명령어로 어플리케이션 필드
5. Babel, PostCSS, Webpack과 같은 모던 빌드 도구 활용하여 최신 JS 문법 사용
6. 빌드 자동화로 JAMstack 마크업 변경사항 실시간 확인
### DEPLOYMENT
- Github Pages + CloudFlare: 무료
    - githubpages jekyll 기반의 기본템플릿 지원
        - Github저장소 1GB 사용제한 월100GB 대역폭 시간당 10개빌드, 빌드가 필요한경우 결과물을 특정 디렉토리 혹은 브랜치에 보관 필요
    - cloudFlare: CDN 업체
        - 역방향 프록시 역할수행
        - 무료로 전세계 CDN및 무료로 CDN 및 SSL인증서, DDos 방어 서비스 제공
        - 개인 도메인을 소유하고 있어야하며, 네임서버를 CloudFlare로 설정 필요
- Netlify: 무료
    - GitHub/BitBucket/Gitlab과 계정 연동및 쉬운 프로젝트 호스팅 제공
    - 무료로 CDN 및 SSL인증서 지속적인 배포 제공
    - 공식 api및 cli 도구 제공
    - 개인도메인을 소유하고 있어야하며, 네임서버를 해당으로 사용
- AWS S3 + CloudFront: 유료
    - AWS상에서 서비스를 운영하는 경우
## DEMO
### Githubpages
### netlify
- 메인에 깃허브에서 가져오는것이 가능
## 요약
서비스 목적에 맞는 웹 기슬수택을 선택
목적과 맞다면 웹서비스 설계시, JAMstack을 고려하자
## 옴니어스 개발자 모집