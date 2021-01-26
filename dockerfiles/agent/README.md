## COMMAND1 to build RedHat image

```console
   $ cd ecea-docker/build
   $ ./build.sh -c=/tmp/test -t=agent -s=rh
```

## COMMAND2 to build ubuntu image
```console
   $ cd ecea-docker/build
   $ ./build.sh -c=/tmp/test -t=agent -s=ubuntu
```

## COMMAND3 to build centos image

```console
   $ cd ecea-docker/build
   $ ./build.sh -c=/tmp/test -t=agent -s=centos
```

## COMMAND4 to rebuild RedHat image from existed ecloud.tar.gz file 

```console 

   $ CONTENT_FOLDER=/tmp/test
   $ mkdir -r $CONTENT_FOLDER/agent
   $ cp ../from/ecloud.tar.gz  to $CONTENT_FOLDER/agent 
   $ cd ecea-docker/build && \
  ./build.sh -t=agent \
   -c=$CONTENT_FOLDER \
   -s=rh \
   -r 
```

## USAGE
```
    "Usage: ./build.sh -t=<build_target> -c=<content_folder> -s=<system_name> [-v=<build_version>]"
    "1 -t=*| --target=*          : <build_target>   - agent | cm | emake"
    "2 -v=*| --version=*         : <build_version>  - in format like 10.0 - optional"
    "3 -c=*| --content_folder=*  : <content_folder> - build folder to prepare content for acceletor-target docker image and build image from it"
    "4 -s=*| --system=*          : <system_name>    - rh | centos | ubuntu" 
    "5 -r  | --reuse - tell to the build image  process to reuse tar archive (if it was prepared earlier) instead of creating new one - optional" 
    "6 -o  | --onlytar - tar from /opt/ecloud to the tarball with name ecloud.tar.gz and exit
           should be used with flags : --target, --content_folder --system"
    "7 -h  | --help  - print help" 
```
