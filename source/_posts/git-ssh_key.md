---
title: git-ssh_key
tag: git
category: git
date: 2019-12-04 21:40:29
---
# 2. SSH Key 관련
## SSH Key 생성
```
$ ssh-keygen -t rsa -C "yourEmail@example.com"
Generating public/private rsa key pair.
Enter file in which to save the key (/c/Users/yourUserDirectory/.ssh/id_rsa):
Created directory '/c/Users/yourUserDirectory/.ssh'.
Enter passphrase (empty for no passphrase):
Enter same passphrase again:
Your identification has been saved in /c/Users/yourUserDirectory/.ssh/id_rsa.
Your public key has been saved in /c/Users/yourUserDirectory/.ssh/id_rsa.pub.
```
## SSH Key 생성 결과
```
The key fingerprint is:
SHA256:[핑거프린트] yourEmail@example.com
The key's randomart image is:
+---[RSA 2048]----+
|     [생략]      |
+----[SHA256]-----+
```
## Github에 공개키 등록
Personal Settings -> SSH and GPG Keys -> New SSH Key -> Key 내용에 id_rsa.pub 내용 복사
## 공개키 확인
```
$ cat ~/.ssh/id_rsa.pub
ssh-rsa [공개키 내용] yourEmail@example.com
```
## 동작 확인
```
$ ssh -T git@github.com
The authenticity of host 'github.com (192.30.255.113)' can't be established.
RSA key fingerprint is SHA256:[핑거프린트].
Are you sure you want to continue connecting (yes/no)? 
```