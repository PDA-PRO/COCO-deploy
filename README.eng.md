[한국어](https://github.com/PDA-PRO/COCO-deploy/blob/main/README.md)|English
## DEMO
- http://codingcoach.co.kr/

## Environmental preparation

### Linux

- System: Ubuntu 20.04.6 LTS

1. Docker installation

   ```bash
   sudo apt update
   sudo apt install apt-transport-https ca-certificates curl gnupg-agent software-properties-common
   curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
   sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable"
   sudo apt-get update
   sudo apt-get install docker-ce docker-ce-cli containerd.io
   sudo usermod -aG docker
   sudo curl -L "https://github.com/docker/compose/releases/download/v2.5.0/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose
   sudo chmod +x /usr/local/bin/docker-compose
   ```

2. Install Docker Compose

   ```bash
   sudo curl -L "https://github.com/docker/compose/releases/download/v2.5.0/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose
   sudo chmod +x /usr/local/bin/docker-compose
   ```

For other ways to install Docker and Docker Compose, see [https://docs.docker.com/install/](https://docs.docker.com/install/)

### Windows

- System: Windows 10

1. Install Docker Desktop  
   [Install Docker Desktop](https://docs.docker.com/desktop/install/windows-install/)

## Installation

1. Select a location with enough space and run the following command

   ```bash
   git clone https://github.com/PDA-PRO/COCO-deploy.git
   cd COCO-deploy
   ```

2. Download Docker image

   ```bash
   docker compose pull
   ```

   Depending on network speed, the time to download all images may vary.

3. Start service

   ```bash
   docker compose up
   ```

   Depending on the performance of your desktop, it may take 5 to 10 minutes for all settings to be completed.

## Execution

You can use it by accessing port http://localhost:80 through a browser.  
The initially set administrator ID is `admin` and the password is `admin1234!`.  
Also, the MySQL password is `qwer1234`.  
You can view the API document when connecting to http://localhost:1000/docs .  
If you would like to add additional **`plugins`**, please visit https://github.com/PDA-PRO/COCO-plugin

## Setting environment variables

You can modify DB information, JWT expiration period, and initial admin account by modifying the environment variable file in the `env` folder.

## Q&A
