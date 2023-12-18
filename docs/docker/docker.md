## 操作远程仓库的命令

login：登录到远程仓库 login命令可以登录到远程仓库，登录到远程仓库后可可以拉取仓库的镜像了  
login语法

```docker
    docker login [OPTIONS] [SERVER]
```

    OPTIONS：可选参数
    SERVER：远程仓库的地址，默认为docker官方仓库，也就是 https://hub.docker.com/

#### OPTIONS的常用值

```docker
    -u string：用户名
    -p string：密码
```

###### login常用写法

使用helianxiaowu用户登录远程仓库，密码为123456

```docker
docker login -u helianxiaowu -p 123456 192.168.10.10/docker-lib
```

不指定用户登录到远程仓库，这时会提示输入用户名或密码

```docker
    docker login 192.168.10.10/docker-lib
```

不指定用户登录到默认的远程仓库，也会提示输入用户名或密码

```docker
docker login
```

## search：从远程仓库搜索镜像

search命令可以从远程仓库搜索镜像

```shell
root@ecs-chenheyi01:/data# docker search mysql
NAME                            DESCRIPTION                                     STARS     OFFICIAL   AUTOMATED
mysql                           MySQL is a widely used, open-source relation…   14467     [OK]       
mariadb                         MariaDB Server is a high performing open sou…   5521      [OK]       
percona                         Percona Server is a fork of the MySQL relati…   621       [OK]       
phpmyadmin                      phpMyAdmin - A web interface for MySQL and M…   866       [OK]       
```

#### search语法

```docker
docker search [OPTIONS] TERM
```

      OPTIONS：可选参数
      TERM：镜像的关键词

#### OPTIONS的常用值

      -f filter: 根据条件过滤镜像，过滤条件详见下文
      no-trunc：显示完整的镜像描述。默认情况下，搜索出来的镜像的描述太长的话会隐藏，no-trunc参数会让镜像信息完整的展示出来
      --limit int: 限制搜索出来的镜像的个数，最大不能超过100个，默认25个
      --format string: 指定镜像显示的格式，格式详见下文
      -f参数表示根据条件过滤搜索出来的镜像，语法如下
      docker search -f KEY=VALUE TERM

#### KEY的可选值如下

      stars int: 根据热度过滤，如：stars=10表示过滤热度大于10的镜像
      is-automated boolean: 根据是否自动构建过滤，如：is-automated=false表示过滤非自动构建的镜像
      is-official boolean: 根据是否官方发布过滤，如：is-official=false表示过滤非官方发布的镜像
      --format参数用来指定搜索出来的镜像的显示的格式，语法如下。table表示使用表格的方式显示，支持\t格式
      docker search --format "[table] {{COLUMN}}[{{COLUMN}}...]" TERM

#### COLUMN的可选值如下：

      .Name：显示镜像的名称列
      .Description：显示镜像的描述列
      .StarCount：显示镜像的热度一列
      .IsOfficial：显示镜像是否是官方发布一列
      .IsAutomated：显示镜像是否是自动构建一列

#### search常用写法

搜索centos镜像

```docker
docker search centos
```

搜索centos镜像，只展示5个

```docker
docker search --limit 5 centos
```

搜索热度大于100并且不是自动构建的centos镜像

```docker
docker search -f stars=100 -f is-automated=true centos
```

搜索非官方发布的centos镜像，搜索结果只展示名称和热度，列之间用TAB键隔开

```docker
docker search -f is-official=false --format "table{{.Name}}\t{{.StarCount}}" centos
```

## push：把本地镜像推送到远程仓库

push可以把本地仓库中的镜像推送到远程仓库，不过需要先登录远程仓库

### push用法

```docker
docker push [OPTIONS] NAME[:TAG]
```

    OPTIONS：可选参数
    NAME：镜像名称
    TAG：镜像版本号，可省略，默认为latest

### OPTIONS的常用值

    --disable-content-trust：推送时远程仓库不校验签名，默认为true

### push常用写法

将my-image镜像的1.1.0版本推送到远程仓库

```docker
docker push my-image:1.1.0
```

将my-image镜像推送到远程仓库，不指定版本时默认为latest版本

```docker
docker push my-image
```

    pull：从远程仓库拉取或更新镜像
    pull命令可以从远程仓库拉取镜像，如果本地仓库已经存在该镜像，则会更新

### pull语法

```docker
docker pull [OPTIONS] NAME[:TAG|@DIGEST]
```

    OPTIONS：可选参数
    NAME：镜像名称
    TAG：镜像版本号，可省略，默认为latest
    DIGEST：镜像的摘要，每个镜像都有对应的名称、id、摘要信息，每个摘要信息能唯一代表一个镜像，比如下图

### OPTIONS的常用值

    -a: 拉取镜像的所有版本号
    --disable-content-trust：推送时远程仓库不校验签名，默认为true
    -q: 安静模式，推送过程中不展示详细信息

### pull常用写法

从远程仓库拉取centos镜像，不指定版本时默认为latest版本

```docker
docker pull centos
```

使用安静模式从远程仓库拉取版本号为5.11的centos镜像

```docker
docker pull -q centos:5.11
```

使用安静模式从远程仓库拉取所有版本号的centos镜像

```docker
docker pull -a -q centos
```

## 操作本地镜像的命令
### images：显示所有镜像
images命令可以显示本地存在的所有镜像
```shell
root@ecs-chenheyi01:/data# docker images
REPOSITORY               TAG                IMAGE ID       CREATED         SIZE
postgres                 latest             a373cbdcfe8b   5 days ago      418MB
postgres                 <none>             69e765e8cdbe   13 days ago     412MB
minio/minio              latest             380be81abf22   5 weeks ago     276MB
nginx                    1.23.4             a7be6198544f   4 months ago    142MB
sonarqube                8.9.10-community   4009139ebd19   9 months ago    490MB
wurstmeister/kafka       latest             a692873757c0   16 months ago   468MB
sonarqube                9.1.0-community    b20fade372bc   22 months ago   560MB
sonarqube                8.9.3-community    dba1ad9ae9aa   22 months ago   509MB
postgres                 9.6.23             8f39a959063c   23 months ago   200MB
garland/aws-cli-docker   latest             f6bfd82c5b75   4 years ago     162MB
wurstmeister/zookeeper   latest             3f43f72cb283   4 years ago     510MB
```
### images语法
```docker
docker images [OPTIONS] [REPOSITORY[:TAG]]
```
    OPTIONS：可选参数
    REPOSITORY：镜像路径
    TAG：镜像版本
### OPTIONS的常用值
    -a: 显示所有镜像，包含中间映像（默认情况下中间映像是隐藏的）
    -f filter: 根据条件过滤镜像，过滤条件详见下文
    -q: 只显示镜像id
    no-trunc：显示完整的镜像id。默认情况下，镜像的id只显示前12位，no-trunc参数会将镜像id完整的显示出来
    --digests：显示镜像的摘要信息
    --format string: 指定镜像显示的格式，格式详见下文
* `-f`参数表示根据条件过滤要显示的镜像，语法如下
```docker
docker images -f KEY=VALUE [REPOSITORY[:TAG]]
```
* KEY的可选值如下
    dangling boolean： 过滤悬挂的镜像，如：dangling=true表示只显示悬挂的镜像
    label string: 根据标签过滤，如：label=version表示显示有version标签的镜像，label=version=1.0表示显示version=1.0的镜像
    before image: 显示在某个镜像之前创建的镜像，如：before=centos:5.8表示显示在centos:5.8这个镜像之前创建的镜像
    since image: 显示在某个存在之后创建的镜像，如：since=centos:5.8表示显示在centos:5.8这个镜像存在之后的镜像
    reference string：模糊匹配，如：reference=cent*:5*, 显示名称已cent开头版本号已5开头的镜像
* `--format`参数用来指定镜像显示格式，语法如下。table表示使用表格的方式显示，支持\t格式
```docker
docker images --format "[table] {{COLUMN}}[{{COLUMN}}...]" [REPOSITORY[:TAG]]
```
* `COLUMN`的可选值如下：

        .ID：显示镜像的名称列
        .Repository：显示镜像的描述列
        .Tag：显示镜像的热度一列
        .Digest：显示镜像是否是官方发布一列
        .CreatedSince：显示镜像是否是自动构建一列
        .CreatedAt：显示镜像是否是自动构建一列
        .Size：显示镜像是否是自动构建一列
### images常用写法
显示本地所有镜像
```docker
docker images
```
显示本地所有镜像，只显示id列并且不截断
```docker
docker images -q --no-trunc
```
显示centos镜像信息
```docker
docker images centos
```
显示列中包含cent关键字的所有镜像
```docker
docker images | grep cent
```
显示本地所有镜像，并显示摘要列
```docker
docker images --digests
```
显示在cengos:latest镜像之后创建的latest版本的所有镜像
```docker
docker images -f since=centos:latest -f reference=*:latest
```
显示所有镜像信息，只显示镜像id、摘要、创建时间3列，列之间用TAB键隔开
```docker
docker images --format "table {{.ID}}\t{{.Digest}}\t{{.CreatedAt}}"
```
显示在centos:5.11镜像之前创建的镜像，只显示镜像仓库路径、版本号、创建时间3列，列之间用TAB键隔开
```docker
docker images -f before=centos:5.11 --format "table {{.Repository}}\t{{.Tag}}\t{{.CreatedAt}}"
```
## rmi：删除本地镜像
rmi命令可以删除一个或多个本地镜像，通常情况应该用rm表示删除命令，但是在doker命令中rm表示删除容器，所以用rmi表示删除镜像，其中的i是image的首字母
### rmi语法
```docker
docker rmi [OPTIONS] IMAGE [IMAGE...]
```
    OPTIONS：可选参数
    IMAGE：镜像id或仓库路径名称
### OPTIONS的常用值
    
    -f: 强制删除，如果镜像有对应的容器正在运行，则不允许直接删除镜像，需要强制删除
    --no-prune：不删除该镜像的过程镜像，默认是删除的
## rmi常用写法
删除centos镜像
```docker
docker rmi tomcat
```
删除centos:5.11镜像
```docker
docker rmi centos:5.11
```
删除id为621ceef7494a的镜像
```docker
docker rmi 621ceef7494a
```
同时删除tomcat、centos和redis镜像
```docker
docker rmi tomcat centos redis
```
强制删除tomcat镜像，就算此时有tomcat容器正在运行，镜像也会被删除
```docker
docker rmi -f tomcat
```
## tag：标记镜像，将其归入仓库
tag命令可以基于一个镜像，创建一个新版本的镜像并归入本地仓库，此时该镜像在仓库中存在两个版本，可以根据这两个镜像创建不同的容器

### tag语法
```docker
docker tag SOURCE_IMAGE[:TAG] TARGET_IMAGE[:TAG]
```
    SOURCE_IMAGE: 原镜像
    TARGET_IMAGE：新镜像
    TAG：镜像的版本号
### tag的常用写法
基于redis:latest镜像创建my-redis1.0镜像，并把新镜像归入redis-lib仓库
```docker
docker tag redis:latest redis-lib/my-redis:1.0
```
基于621ceef7494a镜像创建my-redis:test-100m镜像，并把新镜像归入redis-lib仓库
```docker
docker tag 621ceef7494a redis-lib/my-redis:test-100m
```
## history：查看镜像的创建历史
history命令用来查看某一个镜像的创建历史，也就是镜像的提交记录
### history语法
```docker
docker history [OPTIONS] IMAGE
```
    OPTIONS：可选参数
    IMAGE：镜像
### OPTIONS的常用值
    -H boolean: 已可读的格式打印日期和大小，默认为true
    -q: 只显示镜像id
    no-trunc：输出结果不截取，正常情况下查看到的结果如果某一列太长会被截取
    --format string: 指定镜像显示的格式，格式详见下文
    --format数用来指定镜像的显示的格式，语法如下。table表示使用表格的方式显示，支持\t格式
```docker
docker history --format "[table] {{COLUMN}}[{{COLUMN}}...]" IMAGE
```
### COLUMN的可选值如下：
    .ID：镜像的ID
    .CreatedSince：镜像创建的时长
    .CreatedAt：镜像创建的时间戳
    .CreatedBy：镜像创建使用的命令
    .Size：镜像的大小
    .Comment：镜像的评论
### history常用写法
显示centos镜像的创建历史
```docker
docker history centos
```
显示centos镜像的创建历史，时间和大小转换为人类可读的格式
```docker
docker history -H=true centos
```
显示centos镜像的创建历史，只显示ID、创建时间戳和创建时的命令3列，列之间使用TAB键隔开
```docker
docker history --format "table {{.ID}}\t{{.CreatedAt}}\t{{.CreatedBy}}" centos
```
## save：将镜像打包成文件
save命令可以把一个镜像或多个镜像打包到一个文件中，需要特别注意和export命令的区分
save命令打包的是镜像，包含镜像的所有信息
exprot命令打包的是容器，只是保存容器当时的快照，历史记录和元数据信息将会丢失，详见exprot命令介绍

### save语法
```docker
docker save [OPTIONS] IMAGE [IMAGE...]
```
    OPTIONS：可选参数
    IMAGE：镜像
### OPTIONS的常用值
    -o string: 指定目标文件，和linux原生命令>有相同作用
### save常用写法
将centos镜像打包成my-images.tar
```docker
docker save centos > /home/my-images.tar
```
将centos镜像和redis镜像打包到my-images.tar
```docker
docker save centos redis > /home/my-images.tar
```
将centos镜像和redis镜像打包到my-images.tar
```docker
docker save -o /home/my-images.tar centos redis
```  
## load：从指定文件中加载镜像
load命令可以从指定文件中加载镜像，该文件需要是save命令保存的文件
### load语法
```docker
docker load [OPTIONS]
```
    OPTIONS：可选参数
### OPTIONS的常用值
    -i string: 指定文件的路径
    -q：安静模式输出