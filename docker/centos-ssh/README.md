``` bash
git clone https://github.com/mds1455975151/tools.git
cd tools/docker/centos-ssh
docker build . -t centos-ssh:7.2

docker rm $(docker ps -a -q) 

id=n  # 1 2 3 .. 9
docker run -d -it -p 20${id}0${id}:22 --name os-0${id} centos-ssh:7.2

docker run -d -it -p 20101:22 --name os-01 centos-ssh:7.2
docker run -d -it -p 20202:22 --name os-02 centos-ssh:7.2
docker run -d -it -p 20303:22 --name os-03 centos-ssh:7.2


docker inspect --format='{{range .NetworkSettings.Networks}}{{.IPAddress}}{{end}}' os-01
ssh -p 22 172.17.0.2

镜像默认账号密码：root:123456
```