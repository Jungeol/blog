---
title: linux-User
tag: linux
category: linux
date: 2019-12-04 21:40:29
---
# User
## 유저 추가
```bash
# Create a user
$ sudo adduser your-user-name
# Grant uper user permission
$ sudo usermod -G sudo your-user-name
```
## 그룹 추가
```bash
# Enter prefer group name
$ sudo groupadd your-group-name
```
## 유저를 그룹에 추가
```bash
 $ sudo usermod -a -G your-group-name your-user-name
```
## User List
### username 리스트
```bash
$ cut -d: -f1 /etc/passwd
```
### group 리스트
```bash
$ cut -d: -f1 /etc/group
```
### 그룹 내 사용자 리스트
```bash
$ getent group 그룹이름
```