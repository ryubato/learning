# docker 101

## 참조

* **Docker (Compose) 활용 - 개발 환경 구성하기** https://www.slideshare.net/raccoonyy/docker-compose-usages

* **Docker vs VM** https://medium.com/@darkrasid/docker%EC%99%80-vm-d95d60e56fdd

* **초보를 위한 도커 안내서** https://subicura.com/2017/01/19/docker-guide-for-beginners-1.html

* **Git을 이용한 협업 워크플로우 배우기** http://blog.appkr.kr/learn-n-think/comparing-workflows/

## 개념

docker 이전에는 서버나 개발 환경 구성 시 OS 및 App 버전에 따라 호환성 문제가 많이 발생하여 작업에 많은 시간이 소모되었다. 이런 호환성 문제를 해결하여 docker는 App가 OS에서 독립적으로 실행 될 수 있게 만들었다.

Java의 JVM 처럼 docker engine 만 있으면 OS에 상관없이 App를 실행 할 수 있다.

VM : Server > OS > Hypervisor > 가상 OS > Libs & App 구동

docker : Server > OS > Docker Engine > Container(Libs & App)

docoker 는 동시에 여러개의 Container 를 실행 할 수 있다.

VM 과의 차이점은 Container 와 Conatiner Image의 Layer 구성이다.

장점 : VM 에 비해 생성 & 복구가 빠르고, 용량도 적게 차지한다.

단점 : VM 에 비해 보안이 취약하고, 멀티 OS 구성이 안된다.


## 설치

Windows 7

* Hyper-V 지원이 안되는 Windows 7 에서는 Native 설치가 안된다. Windows 10 이상 지원

* Windows 7 에서는 Docker ToolBox 설치. (Oracle VirtualBox로 가상 Linux System 에 Docker 설치)

* 설치파일 & 방법: https://docs.docker.com/toolbox/toolbox_install_windows/

Windows 10
* 설치파일 & 방법: https://store.docker.com/editions/community/docker-ce-desktop-windows

## 기본 사용법

