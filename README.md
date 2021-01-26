# Cloudbees CD Accelerator Dockerize 프로젝트
 
## 리소스 준비

  1. Sharefile 에서  Container 릴리즈 gzip 파일을 다운받아 ecloud.tar.gz 를 추출
  2. 소스 다운로드
  ```console
    $ git clone https://github.com/kin3303/cbca-docker.git
  ```
  3. ecloud.tar.gz 파일을 원하는 타입의 Dockerfile 위치로 붙여넣기
  - [*ClusterManager*](https://github.com/kin3303/cbca-docker/blob/master/dockerfiles/cm)
  - [*Agent*](https://github.com/kin3303/cbca-docker/tree/master/dockerfiles/agent)
  - [*Emake*](https://github.com/kin3303/cbca-docker/tree/master/dockerfiles/agent)  
