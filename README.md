# Cloudbees Accelerator Dockerize 프로젝트

## EFS 파일시스템 설치

  1. EFS 파일 시스템을 호스트 머신에 설치한다.

  ```console
    $ sudo su
    $ chmod +x ElectricAcceleratorFileSystem-11.1.0.88023-Linux-x86_64-Install
    $ ./ElectricAcceleratorFileSystem-11.1.0.88023-Linux-x86_64-Install
    InInstalling Linux EFS... 
    LOFS compiled and installed successfully.
    Installation complete.
  ``` 

## 이미지 빌드

  1. Sharefile 에서  Container 릴리즈 gzip 파일을 다운받아 ecloud.tar.gz 를 추출
  2. 소스 다운로드
  ```console
    $ git clone https://github.com/kin3303/cbca-docker.git
  ```
  3. ecloud.tar.gz 파일을 빌드하려는 타겟 도커파일이 있는 위치에 붙여넣기
  ```console
     $ cp ecloud.tar.gz cbca-docker/dockerfiles/agent/
  ```
  
  4. 이미지를 빌드
  - [*ClusterManager*](https://github.com/kin3303/cbca-docker/blob/master/dockerfiles/cm)
  - [*Agent*](https://github.com/kin3303/cbca-docker/tree/master/dockerfiles/agent)
  - [*Emake*](https://github.com/kin3303/cbca-docker/tree/master/dockerfiles/agent)  
  
  
## 이미지 실행

### Cluster Manager
  
  ```console
     # 컨테이너 실행
     $ docker run  -i -d -t  -p 80:80 -p 8030:8030 -p 8031:8031 -p 443:443 -p 3306:3306 --name=<컨테이너명> <이미지명>
     
      # 컨테이너 실행
     $ docker top  <컨테이너명>
     $ docker logs  <컨테이너명>
     $ docker exec -it <컨테이너명> bash
  ```
  
### Agent
  
  - 컨테이너 실행
  ```console
       $ docker run --privileged=true  -idt \
       -e CM_HOST_AND_PORT=<CM_IP주소>:<CM_포트> \
       -e AGENT_RESOURCE=linux  \
       -e EFS_ID=1  \
       --device /dev/efs \
       --net=host \
       --hostname=test
       --name=<컨테이너명> <이미지명>
  ```


docker run --privileged=true -idt -e CMHOST=*\<host\[:port\]\>* -e EFS_ID= --device /dev/efs --net=host [--name=] [--hostname=]


  - 실행확인  
  ```console
       $ docker top  ec_agents
       $ docker logs  ec_agents
  ```
  
  - 빌드
  ```console
     $ docker exec  <컨테이너명> /opt/ecloud/i686_Linux/64/bin/emake -v
     $ docker exec  <컨테이너명> /opt/ecloud/i686_Linux/64/bin/emake -f /tmp/Makefile
  ```
  
  - Bash 쉘로 접근

  ```console
     $ docker exec -it <컨테이너명> bash
  ```
  
### Emake
  
  - 컨테이너 실행
  
  ```console
      docker run -it -d -v /home/dev/prj:/home/dev/prj  -w /home/dev/prj --name=<컨테이너명> <이미지명>
  ```   
