한국어|[English](https://github.com/PDA-PRO/COCO-deploy/blob/main/README.eng.md)

## DEMO

- 웹사이트 http://codingcoach.co.kr/
- 데모 비디오 https://youtu.be/QmN3g7kjjw4

## 환경 준비

### Linux

- System: Ubuntu 20.04.6 LTS

1. 도커 설치

   ```bash
   sudo apt update
   sudo apt install apt-transport-https ca-certificates curl gnupg-agent software-properties-common
   curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
   sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable"
   sudo apt-get update
   sudo apt-get install docker-ce docker-ce-cli containerd.io
   sudo usermod -aG docker
   ```

2. 도커 컴포즈 설치

   ```bash
   sudo curl -L "https://github.com/docker/compose/releases/download/v2.5.0/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose
   sudo chmod +x /usr/local/bin/docker-compose
   ```

도커, 도커 컴포즈를 설치할 다른 방법은 [https://docs.docker.com/install/](https://docs.docker.com/install/)을 참조하세요

### Windows

- System: Windows 10

1. 도커 데스크탑 설치  
   [도커 데스크탑 설치](https://docs.docker.com/desktop/install/windows-install/)

## 설치

1. 공간이 충분한 위치를 선택하고 다음 명령을 실행하세요

   ```bash
   git clone https://github.com/PDA-PRO/COCO-deploy.git
   cd COCO-deploy
   ```

2. 도커 이미지 다운

   ```bash
   docker compose pull
   ```

   네트워크 속도에 따라 모든 이미지를 다운받는 시간이 달라질 수 있습니다.

3. 서비스 시작

   ```bash
   docker compose up
   ```

   데스크탑의 성능에 따라 모든 설정이 끝날떄까지 5~10분이 소요됩니다.

## 실행

브라우저를 통해 http://localhost:80 포트로 접속하여 이용하실 수 있습니다.  
기본적으로 설정되어 있는 관리자의 계정은 아이디 `admin` 비밀번호 `admin1234!`입니다.  
또한 MySQL 비밀번호는 `qwer1234`입니다.  
http://localhost:1000/docs 로 접속시 API 문서를 조회할 수 있습니다.  
`플러그인`을 추가하고 싶다면 https://github.com/PDA-PRO/COCO-plugin 를 방문해주세요

## 환경 설정

`env` 폴더의 환경변수 파일을 수정하여 DB 정보, JWT 만료 기간, 최초 어드민 계정을 수정할 수 있습니다.

## FAQ

### 도커 권한 문제

아래와 같은 오류 메시지와 함께 `docker pull` 명령어가 작동하지 않는다

```
Got permission denied while trying to connect to the Docker daemon socket at unix:///var/run/docker.sock: Get http://%2Fvar%2Frun%2Fdocker.sock/v1.40/containers/json: dial unix /var/run/docker.sock: connect: permi
ssion denied
```

### 해결 방법

docker group에 해당 유저 추가

```
sudo groupadd docker
sudo usermod -aG docker $USER
newgrp docker
```

---
