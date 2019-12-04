---
title: seminar-ubuntu17.11.04
tag: seminar
category: seminar
date: 2019-12-04 21:40:29
---
# 우분투한국커뮤니티 11월 대전지역세미나
2017.11.03
## 개발자를 위한, 윈도 10으로 시작하는 우분투 리눅스
MS mvp 남정현
### WSL
- ELF64 바이너리 수준의 호환성 보장
- Windows에너 리눅스 실행
- cygwin과 비교시 명확한 장점
- docker와 가장 유사
### 제한
- 커널 관련 업데이트
- 가상화기술, 애찯ㄱ zjsxpdlsj
- OpenGL, SDL 등 멀티미디어 기능
- 데몬, 자동실행되는 백그라운드 서버
### case by case
- X11 apps
- Tenserflow, GPU 안됨
### 상호 운영성
- Linux -> Window: ok
- Windows -> Lunux: 파일은 보이나 연동은 X
### 리눅스 간편 초기화
- 앰에서 unbuntu 검색후 고급옵션 -> 초기화
### 상호연동
- bash.exe
- wslconfig.exe
#### 코드 예시
```
CallUbuntu "ls -al /"
``` 
### x window
- Xming, VCXSRV
- OpenGl이 필요한경우 후자
### 발표자료
- https://www.medium.com/@rkttu
- 
## LTE-M 이동통신과 IoT
### LTE망을 이용한 전용 프로토콜
## 임베디드SW와 보안
## owasp -> 공통적으로 발생하는 보안이슈 정보