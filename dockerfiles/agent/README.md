## COMMAND1 to build RedHat image

```console
   $ cd cbca-docker/build
   $ ./build.sh -c=/tmp/test -t=agent -s=rh
```

## COMMAND2 to build ubuntu image
```console
   $ cd cbca-docker/build
   $ ./build.sh -c=/tmp/test -t=agent -s=ubuntu
```

## COMMAND3 to build centos image

```console
   $ cd cbca-docker/build
   $ ./build.sh -c=/tmp/test -t=agent -s=centos
```

## COMMAND4 to rebuild RedHat image from existed ecloud.tar.gz file 

```console 

   $ CONTENT_FOLDER=/tmp/test
   $ mkdir -r $CONTENT_FOLDER/agent
   $ cp ../from/ecloud.tar.gz  to $CONTENT_FOLDER/agent 
   $ cd cbca-docker/build && \
  ./build.sh -t=agent \
   -c=$CONTENT_FOLDER \
   -s=rh \
   -r 
```

## USAGE

```
    "Usage: ./build.sh -t=<build_target> -c=<content_folder> -s=<system_name> [-v=<build_version>]"
    
        "1 빌드 타겟 설정 
            -t=* | --target=*  (agent, cm, emake 중 택1)
        "2 버전 정보 설정 (Optional)
             -v=*| --version=*  (11.0, 12.0 ..)
        "3 작업 폴더 설정 
             -c=*| --content_folder=*  
             이미지 빌드시 사용할 작업 폴더 
        "4 베이스 OS 설정
             -s=*| --system=*  (rh, centos, ubuntu 중 택1)
        "5 ecloud.tar.gz 파일 재사용
             -r | --reuse 
```
