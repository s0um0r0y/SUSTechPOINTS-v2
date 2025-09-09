### Docker

#### Build Image yourself
```
cd Docker

# Build docker image (构建镜像)

docker build -t sustechpoints:v1.0.0 .

# Create container of server ,Please replace ${YourDataPath} with the path where you put data on

docker run -it -d --restart=always --name STPointsSServer -p 8081:8081 -v ${YourDataPath}:/root/SUSTechPOINTS/data sustechpoints:v1.0.0 bash
# or use this
docker run -it --name STPointsSServer -p 8081:8081 -v /scratch/soumo_roy/aug5_sustech:/root/SUSTechPOINTS-v2/data sustechpoints:v1.0.0 bash

# to stop the system use
docker rm STPointsSServer

# to enter the container use and to move data use 
docker exec -it STPointsSServer bash .
```
