---
title: linux-SFTP
tag: linux
category: linux
date: 2019-12-04 21:40:29
---
# SFTP 만 로그인 되는 계정 설정
- ssh에서 쉘을 허용할경우 보안 문제가 생김.
- 이때문에 가능한 사용자가 쉘 접근을 하지 못하게 막을 필요가 있음.
- nas의 경우 파일 다운로드 업로드가 주 용도이기 때문에 sftp만 이용할 수 있는 계정만있어도 충분

## 계정 생성
계정생성
- sftp만 로그인 되는 계정은 스스로 비밀번호를 변경할 수 없음
```bash
# 유저 생성
$ sudo useradd some-user-name
# 패스워드 설정
$ sudo passwd some-user-name
```

## sshd_config 수정
config file 접근
```bash
sudo nano /etc/ssh/sshd_config
```
config file 수정
```bash
#아래 내용 코멘트 처리 후 내용추가
#Subsystem  sftp    /usr/libexec/openssh/sftp-server
Subsystem   sftp internal-sftp
```
```bash
#config file 가장 마지막 부분에 아래 내용을 추가
Match User some-user-name
    ChrootDirectory /some/path/
    ForceCommand internal-sftp
    x11Forwarding no
```
## ssh 서비스 재시작
```bash
$ sudo service ssh restart
```
## 제한사항
1. 소유자는 root여야한다
2. root 이외의 사용자가 접속 '/'경로에 쓰기권한이 있으면 접속이 안된다
3. '/' 경로에 쓰기 권한이 없으니 접속 사용자는 파일업로드가 불가능하다. 접속자 소유의 하위 폴더를 만들어 줘야한다.
```bash
$ sudo chown root:some-group /some/path
$ chmod 755 /some/path
```
## 참고
https://zetawiki.com/wiki/SFTP%EB%A7%8C_%EB%90%98%EB%8A%94_%EA%B3%84%EC%A0%95_%EC%83%9D%EC%84%B1
