---
title: docker-basic
date: 2020-04-07 13:39:33
categories:
    - docker
tags:
    - docker
---

# Docker 기본

## 설치

ubuntu

```bash
curl -fsSL https://get.docker.com/ | sudo sh
```
참고: https://docs.docker.com/install/

버전확인
```bash
sudo docker version
```

sudo 없이 docker사용
- 해당 사용자를 `docker`그룹에 추가한다.

```bash
sudo usermod -aG docker $USER
```

## 컨테이너 실행

```bash
docker run [OPTIONS] IMAGE[:TAG|@DIGEST] [COMMAND] [ARG...]
```

옵션|설명
-|-
-d|백그라운드 모드
-p|호스트와 컨테이너의 포트 포워딩 [h포트:c포트]
-v|호스트와 컨테이너의 디렉토리를 마운트
-e|컨테이너 내에서 사용할 환경변수 설정
-name|컨테이너 이름 설정
-rm|프로세스 종료시 컨테이너 자동 제거
-it|-i와 -t를 동시에 사용한 것으로 터미널 입력을 위한 옵션
–link|컨테이너 연결 [컨테이너명:별칭]

예시

```bash
docker run --rm -it ubuntu:18.04 /bin/bash
```

## 컨테이너 목록 확인

```bash
docker ps [OPTIONS]
```
옵션|설명
-|-
-a|모든 목록

## 컨테이너 중지

```bash
docker stop [OPTIONS] CONTAINER [CONTAINER...]
```

## 컨테이너 제거

```bash
docker rm [OPTIONS] CONTAINER [CONTAINER...]
```

## 이미지 목록확인

```bash
docker images [OPTIONS] [REPOSITORY[:TAG]]
```

## 이미지 다운로드

```bash
docker pull [OPTIONS] NAME[:TAG|@DIGEST]
```

## 이미지 삭제

```bash
docker rmi [OPTIONS] IMAGE [IMAGE...]
```

## 컨테이너 로그

```bash
docker logs [OPTIONS] CONTAINER
```

옵션|설명
-|-
--tail [num]|마지막 줄만 보기
-f|실시간 로그 보기

## 컨테이너 명령 실행

```bash
docker exec [OPTIONS] CONTAINER COMMAND [ARG...]
```