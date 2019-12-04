---
title: git-basic
tag: git
category: git
date: 2019-12-04 21:40:29
---
# 1.최초 설정
## 사용자 이름과 메일 주소 설정
```
$ git config --global user.name "FirstName Lastname"
$ git config --global user.email "yourEmail@example.com"
```
## 명령어 UI 기본 설정
```
$ git config --golobal color.ui auto
```
## 편집기
```
$ git config --global core.editor {{editorName}}
```
## 설정 확인
모든 설정 보기 / 특정 설정만 보기
```
$ git config --list
$ git config user.name
```
## 설정파일 확인
```
$ cat ~/.gitconfig
[user]
  name = FirstName LastName
  email = yourEmail@example.com
[color]
  ui = auto
  ...
```
# 2. 기본
## 파일 상태 확인
```
$ git status
```
## Modified 상태의 파일을 Stage
```
$ git add {{file or path}}
```
## commit
```
$ git commit
$ git commit -m ""
```
첫째줄: 한줄요약

둘째줄: 공백

셋째줄: 자세히
# 3. 리모트 저장소
## 리모트 저장소 복제
```
$ git clone git://github.com/....
```
## 리모트저장소 확인 / 추가
```
$ git remote -v
$ git remote add {{remote-name}} {{remote-address}}
```
## 리모트 저장소 가져오기
fetch 명령은 마지막 이후 수정된걸 가져옴. 수동으로 머지 필요.
```
$ git fetch {{remote-name}}
```
pull 명령은 자동으로 머지
```
$ git pull {{remote-name}}
```
## 리모트 저장소 Push
```
git push {{remote-name}} {{branch-name}}
```