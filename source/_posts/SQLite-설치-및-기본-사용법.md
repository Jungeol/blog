---
title: '[SQLite] 설치 및 기본 사용법'
date: 2020-02-26 11:02:50
categories:
    - db
    - sqlite
tags:
    - sqlite
---

# SQLite 란?

- 파일기반 작고 빠른 SQL 데이터 베이스 엔진
    - 매우 심플하지만 RDBMS의 기능을 모두 갖추고 있다
    - 생성시 해당 디렉토리에 `{NAME}.db'라는 파일이 생기며 이것을 기반으로 동작 한다
- 안정적이며 크로스플랫폼 지향, 유즈케이스가 많다
- 광범위한 분야에서 매우 일반적으로 사용됨
- 오픈소스이며 라이센스 걱정 없이 쓸 수 있음
- 이전버전과 호환되며 적어도 2050년까지 유지 할 계획

# 설치 방법

## ubuntu

ubuntu 18.04 기준

```bash
$ sudo apt-get install sqlite3 libsqlite3-dev
```

## windows
windows 10 기준

https://www.sqlite.org/download.html

위의 링크에서 `Precompiled Binaries for Windows` 아래의 command-line shell이 포함되어있는 `sqlite-tools-win32-x86-{버전}.zip`을 받는다. 

{% asset_img win-download.PNG %}

압축을 풀어 적당한 경로에 옮겨준다.(예제는 `C:\sqlite3`경로로 진행)

{% asset_img sqlite-unpack.PNG %}

환경변수 설정창에 들어가 Path를 설정해준다.

환경변수 설정창 들어가는 법
1. 작업 표시줄에서 `시스템 환경 변수 편집` 검색
2.  `내 PC` 오른클릭 -> `속성` -> 왼쪽 메뉴 중 `고급 시스템 설정` ->  `고급`탭에 `환경 변수`

{% asset_img path-config-1.png %}

시스템 변수에서 `Path`를 찾아 `편집`버튼을 눌러준다.(사용자 변수도 가능)

{% asset_img path-config-2.png %}

`새로 만들기`버튼을 눌러 이전 sqlite경로를 넣어준후 `확인`한다.

PowerShell이나 cmd에서 버전정보가 나오면 성공이다.

```cmd
> sqlite3 -version
```

{% asset_img sqlite-powershell-version.png %}

# 기본 사용 법

## 접속

```
$ sqlite3 test.db
SQLite version 3.31.1 2020-01-27 19:55:54
Enter ".help" for usage hints.
sqlite>
```
해당 디렉토리의 `test.db`에 접근한다.

- `test.db`라는 파일이 있으면 그쪽에 접근한다.
- 파일이 없으면 초기화된다.(테이블 데이터를 입력한 이후에 파일이 생김)

실행하면 전용 명령창이 실행되며, 여기서 직접 쿼리를 입력하거나 전용 명령어로 동작한다.

## 기본 명령어

### 도움말
`.help`로 도움말을 확인할 수 있다.
```
sqlite> .help
```

### 테이블 목록

```
sqlite> .table
```

### 스키마 확인

```
sqlite> .schema
```
명령어 뒤에 옵션으로 테이블 이름을 쓸 수 있다.

### 접속 종료

```
sqlite> .exit
```

## 쿼리 작성

아래의 예제와 같이 일반 SQL문으로 테이블을 다룰 수 있다.

### CREATE TABLE
```
sqlite> CREATE TABLE TEST(
   ...>     id INTEGER PRIMARY KEY,
   ...>     name VARCHAR(10),
   ...>     number VARCHAR(10)
   ...> );
```

### INSERT

```
sqlite> INSERT INTO TEST(name, number)
   ...> VALUES('홍길동', '01012345678');
```

### SELECT

```
sqlite> SELECT * FROM TEST;
1|홍길동|01012345678
```
`PRIMARY KEY`를 `INTERGER`로 등록하면 입력시 자동으로 값이 증가하는 특성이 있는것 같다.

`.header on`과 `.mode column`등의 명령어로 테이블 출력을 좀더 편하게 볼 수 있다.