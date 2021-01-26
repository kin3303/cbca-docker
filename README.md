# Cloudbees CD Accelerator Dockerize 프로젝트

## 이미지 빌드

  1. Sharefile 에서  Container 릴리즈 gzip 파일을 다운받아 ecloud.tar.gz 를 추출
  2. 소스 다운로드
  ```console
    $ git clone https://github.com/kin3303/cbca-docker.git
  ```
  3. ecloud.tar.gz 파일을 원하는 타입의 Dockerfile 위치로 붙여넣기
  
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
       $ docker run --privileged=true  -i -d -t \
       -e CMHOST=<CM_IP주소>:<CM_포트> \
       -e AGENT_RESOURCE=linux  \
       --device /dev/efs \
       --net=host \
       --name=<컨테이너명> <이미지명>
  ```

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
