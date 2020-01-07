---
title: '[Vagrant] Windows 사용법'
date: 2020-01-07 12:13:10
categories: vagrant
tags: vagrant
---
# [Vagrant] Windows 사용법

## Vagrant란?

- Vagrant는 주로 가상머신을 생성하고 관리할때 사용된다.
- 가상머신의 생성과 설정을 스크립트로 자동화 해주는 도구이다.
- Mac, Liux, Windows 등의 멀티 OS를 지원한다.
- Provider는 기본적으로 VirtualBox기준으로 되어있으며, VMware, Docker, Hyper-V 등도 지원한다.

주소: https://www.vagrantup.com/

## 설치

### VirtualBox

https://www.vagrantup.com/docs/virtualbox/

위의 링크에서 지원하는 VirtualBox의 버전을 확인 후 아래 링크에서 VirtualBox를 받는다.

https://www.virtualbox.org/wiki/Downloads

최신버전을 지원하지 않는 경우, 해당 페이지에서 `VirtualBox older builds`를 찾아 받는다.

### Vagrant

https://www.vagrantup.com/downloads.html

위의 링크에서 `Windows 64-bit`버전을 다운받아 설치한다.

윈도우의 기본 설치경로는 `C:\HashiCorp\Vagrant`이다.

설치가 완료됐다면 cmd나 PowerShell에서 vagrant 명령어를 실행가능하다.

``` bash
$ vagrant -v
Vagrant 2.2.6
```

## 플러그인 설치

아래는 Vagrant의 플러그인들을 정리해놓은 페이지이다.

https://github.com/hashicorp/vagrant/wiki/Available-Vagrant-Plugins


필요한 플러그인이 있다면 아래처럼 설치하면 된다.

``` bash
$ vagrant plugin install {{플러그인 이름}}
```

### 사용중인 플러그인

- vagrant-hostmanager
    - /etc/hosts approach

## 기초 cli 명령어

- vagrant init
    - vagrant의 초기파일(vagrantfile)을 생성한다.
- vagrant up
    - 초기파일(vagrantfile)의 설정에따라 가상머신을 생성한다.
- vagrant halt
    - 가상머신을 종료한다.
- vagrant destroy
    - 가상머신을 삭제한다.
- vagrant ssh
    - 가상머신에 ssh로 접근한다.
- vagrant provision
    - 가상머신의 설정을 변경하고 적용한다.

## 사용법

기본적인 사용법: https://www.vagrantup.com/intro/getting-started/index.html

### 초기화 명령어
```bash
$ vagrant init
```
init 명령어를 실행할경우, 해당 디렉토리에 `Vagrantfile`이라는 파일이 생긴다.

이것은 가상머신을 만들기위한 스크립트 파일이다.

### 스크립트

아래는 centos6 가상머신 3개를 설치하고 초기화 스크립트를 실행하는 `Vagrantfile`이다.

```bash
### 초기화 스크립트
$init_script = <<SCRIPT

yum -y update

yum -y install wget

SCRIPT

Vagrant.configure("2") do |config|

	# Define base image
	config.vm.box = "generic/centos6"

	# Manage /etc/hosts on host and VMs
	config.hostmanager.enabled = false
	config.hostmanager.manage_host = true
	config.hostmanager.include_offline = true
	config.hostmanager.ignore_private_ip = false

    # server01
	config.vm.define :server01 do |server01|
		server01.vm.provider :virtualbox do |v|
			v.name = "server01"
			v.customize ["modifyvm", :id, "--memory", "2048"]
		end
		server01.vm.network :private_network, ip: "192.168.56.101"
		server01.vm.hostname = "server01"
		server01.vm.provision :shell, :inline => $init_script # 초기화 스크립트 실행
	end

    # server02
	config.vm.define :server02 do |server02|
		server02.vm.provider :virtualbox do |v|
			v.name = "server02"
			v.customize ["modifyvm", :id, "--memory", "2048"]
		end
		server02.vm.network :private_network, ip: "192.168.56.102"
		server02.vm.hostname = "server02"
		server02.vm.provision :shell, :inline => $init_script # 초기화 스크립트 실행
	end

    # server03
	config.vm.define :server03 do |server03|
		server03.vm.provider :virtualbox do |v|
			v.name = "server03"
			v.customize ["modifyvm", :id, "--memory", "2048"]
		end
		server03.vm.network :private_network, ip: "192.168.56.103"
		server03.vm.hostname = "server03"
		server03.vm.provision :shell, :inline => $init_script # 초기화 스크립트 실행
	end
end
```

#### Base Image에 대해

```bash
# Define base image
config.vm.box = "generic/centos6"
```

위의 `base image`를 설정하는 부분을 보면과연 이미지는 어디서 가져오는 것이며 다른 이미지를 쓰고싶으면 어디서 찾아야할까? 라는 의문이 생길것이다.

개발사에서 운영하는 `Vagrant Cloud`라는 공식 이미지 저장소가 있다. 아래의 링크에서 검색하여 사용하면 된다.

https://app.vagrantup.com/boxes/search

이곳에는 Ubuntu, Cent OS 등등 메이저 OS의 배포판들은 다있다고 봐도 무방하다.

공개된 Box를 사용하는것은 제한없이 무료이며, 비공개 Box를 업로드하거나 팀원들과 공유하는것은 유료이다.


### 가상머신 생성

위에서 초기화한 디렉토리에서 아래 명령어를 입력하면 스크립트가 실행되며 가상머신이 생성된다.

```bash
$ vagrant up
```

### 가상머신 접속

vagrant에서는 이미지 생성시 자동으로 ssh설정과 함께 private key를 발급해준다.

아래는 가상머신 ssh에 접속하기위한 명령어이다.

```bash
$ vagrant ssh {{저장소이름}}
```