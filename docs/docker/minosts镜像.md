# miniosts 镜像生成

#### 运行一个空白linux服务
```shell 
 docker run -it centos:latest /bin/bash 
> ```

#### 设置软件源信息
 ```shell 
  sed -i 's/mirrorlist/#mirrorlist/g' /etc/yum.repos.d/CentOS-*
  sed -i 's|#baseurl=http://mirror.centos.org|baseurl=http://vault.centos.org|g' /etc/yum.repos.d/CentOS-*  
 ```

#### 安装 vim、wget等工具
```shell
yum install vim wget unzip
```

#### 创建根目录
```shell
mkdir -p /data/minio
mkdir -p /data/logs
midkr -p /data/aws
```

#### 下载软件包
```shell
cd /data/minio
wget http://dl.minio.org.cn/server/minio/release/linux-amd64/minio

cd /data/aws
curl "https://awscli.amazonaws.com/awscli-exe-linux-x86_64-2.0.30.zip" -o "awscliv2.zip" 
```





