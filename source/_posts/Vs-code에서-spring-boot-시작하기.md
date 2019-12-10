---
title: Vs code에서 spring boot 시작하기
date: 2019-12-10 23:13:52
categories:
    - Java
    - Spring Boot
tags:
    - java
    - spring boot
---
# Visual Studio code에서 Spring boot 시작하기

## VS Code 익스텐션 설치

VS Code에서 Spring boot를 사용하기 위해선 아래의 Extension들이 필요하다.

VS Code의 왼쪽 `Extensions 탭`을 열고 키워드를 검색 하여 `Spring Boot Extension Pack`을 설치하도록 하자. 설치를 진행하면 하위의 Extension들이 자동으로 함께 설치된다.

- Spring Boot Extension Pack
    - Spring Boot Tools
    - Spring Initializr Java Support
    - Spring Boot Dashboard

만약 `Java Extension Pack`이 없다면 해당 Extension도 설치해주자.

Maven대신 Gradle을 사용할경우, `Gradle Extension Pack`도 함께 설치해주자.

## 프로젝트 만들기

`Spring Initializr` 익스텐션이 Spring Boot 프로젝트의 초기화를 도와준다.

상단 메뉴의 `View > Command Palett` 또는 `Ctrl + Shift + P`키를 이용해 `Spring Initializr`를 검색한다.

1. 둘 중에 하나를 선택하여 진행하자.

    - Spring Initializr: Generate a Gradle Project
    - Spring Initializr: Generate a Maven Project

2. 진행 언어선택지가 나오는데 `Java`를 선택하도록 하자.

    - Java
    - Kotlin
    - Groovy

3. 프로젝트 Group Id를 지정한다.

    ```
    com.example
    ```

4.  Artifact ID를 지정한다.
    
    ```
    demo
    ```
5. Spring boot 버전을 선택한다.
    
    - `2.2.2`
    - 2.2.3 (SNAPSHOT)
    - 2.1.12 (SNAPSHOT)
    - 2.1.11

6. 추가도구(의존성)을 선택한다.
    
    - Spring Boot DevTools
    - Lombok
    - Spring Web

## 어플리케이션 실행

SPRING-BOOT 대시보드로 실행이 가능하다.

1. `탐색기 > SPRING-BOOT DASHBOARD > 프로젝트이름 > Start` 로 어플리케이션 실행
2. `프로젝트이름` 을 오른 클릭 후 `Open in Browser` 가능
3. 해당 메뉴에서 디버그 모드 실행도 가능하다.

프로젝트 설정시 아래 선택지중 하나를 골랐다면,

- Spring Initializr: Generate a Gradle Project
- Spring Initializr: Generate a Maven Project

초기화 후 바로 실행하 후 아래와 같은 에러 페이지로 연결이 되는데 정상적으로 구동된것이다.

```
Whitelabel Error Page

This application has no explicit mapping for /error, so you are seeing this as a fallback.

Wed Dec 11 00:12:44 KST 2019
There was an unexpected error (type=Not Found, status=404).
No message available
```