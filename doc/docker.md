### Docker

#### Build Image yourself(自行创建镜像, 较为繁琐)
```
cd Docker

# Build docker image (构建镜像)

sudo docker build -t sustechpoints:v1.0.0 .

# Create container of server ,Please replace ${YourDataPath} with the path where you put data on (创建容器, 请将用你的数据存储路径将变量${YourDataPath}替换, 注意数据要符合data/example中的组织方式)

sudo docker run -it -d --restart=always --name STPointsSServer -p 8081:8081 -v ${YourDataPath}:/root/SUSTechPOINTS/data sustechpoints:v1.0.0 bash
# or use this
docker run -it --name STPointsSServer -p 8081:8081 -v /scratch/soumo_roy/aug5_sustech:/root/SUSTechPOINTS-v2/data sustechpoints:v1.0.0 bash

# to stop the system use
docker rm STPointsSServer

# to enter the container use and to move data use 
docker exec -it STPointsSServer bash .
```
