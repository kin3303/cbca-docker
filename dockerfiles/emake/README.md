## COMMAND1 to build RedHat image

```console
   $ cd ecea-docker/build
   $ ./build.sh -c=/tmp/build -t=emake -s=rh
```

## COMMAND2 to build ubuntu image
```console
   $ cd ecea-docker/build
   $ ./build.sh -c=/tmp/build -t=emake -s=ubuntu
```

## COMMAND3 to build centos image

```console
   $ cd ecea-docker/build
   $ ./build.sh -c=/tmp/build -t=emake -s=centos
```

## USAGE
```
    "Usage: ./build.sh -t=<build_target> -c=<content_folder> -s=<system_name> [-v=<build_version>]"
    "1 -t=*| --target=*          : <build_target>   - agent | cm | emake"
    "2 -v=*| --version=*         : <build_version>  - in format like 10.0 - optional"
    "3 -c=*| --content_folder=* : <content_folder> - build folder to prepare content for acceletor-target docker image and build image from it"
    "4 -s=*| --system=*          : <system_name>    - rh | centos | ubuntu" 
    "5 -o  | --onlytar - tar from /opt/ecloud to the tarball with name ecloud.tar.gz and exit
           should be used with flags : --target, --content_folder --system"
    "6 -h  | --help  - print help" 
```
