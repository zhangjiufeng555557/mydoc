# Shell报错syntax error: unexpected end of file

> 执行shell脚本文件，报错syntax error: unexpected end of file。
> 使用vim工具打开脚本文件，却并没有发现有什么问题。

```shell
vim hello.sh

#./bin/bash
# 定义颜色
BLUE_COLOR="\033[36m"
RED_COLOR="\033[31m"
GREEN_COLOR="\033[32m"
VIOLET_COLOR="\033[35m"
RES="\033[0m"

echo -e "${BLUE_COLOR}# ######################################################################${RES}"
echo -e "${BLUE_COLOR}#                       Docker ELK Deploy Script                       #${RES}"
echo -e "${BLUE_COLOR}# ######################################################################${RES}"

# 创建目录
echo -e "${BLUE_COLOR}---> create [elasticsearch]directory start.${RES}"
if [ ! -d "./elasticsearch/" ]; then
mkdir -p ./elasticsearch/master/conf ./elasticsearch/master/data ./elasticsearch/master/logs \
    ./elasticsearch/slave1/conf ./elasticsearch/slave1/data ./elasticsearch/slave1/logs \
    ./elasticsearch/slave2/conf ./elasticsearch/slave2/data ./elasticsearch/slave2/logs
fi
"deploy.sh" [dos] 88L, 3290B     
```

> 但是只需要使用vim+参数的方式打开该文件，就会发现一些端倪。

```shell

#./bin/bash^M
# 定义颜色^M
BLUE_COLOR="\033[36m"^M
RED_COLOR="\033[31m"^M
GREEN_COLOR="\033[32m"^M
VIOLET_COLOR="\033[35m"^M
RES="\033[0m"^M
^M
echo -e "${BLUE_COLOR}# ######################################################################${RES}"^M
echo -e "${BLUE_COLOR}#                       Docker ELK Deploy Script                       #${RES}"^M
echo -e "${BLUE_COLOR}# ######################################################################${RES}"^M
^M
# 创建目录^M
echo -e "${BLUE_COLOR}---> create [elasticsearch]directory start.${RES}"^M
if [ ! -d "./elasticsearch/" ]; then^M
mkdir -p ./elasticsearch/master/conf ./elasticsearch/master/data ./elasticsearch/master/logs \^M
    ./elasticsearch/slave1/conf ./elasticsearch/slave1/data ./elasticsearch/slave1/logs \^M
    ./elasticsearch/slave2/conf ./elasticsearch/slave2/data ./elasticsearch/slave2/logs^M
fi^M
^M
```

> 在每一个shell语句的末尾，都多了一个^M的标志，这其实是因为该文件是在windows环境下编写，然后传输到Linux环境来的，但是因为windows环境的文本有\r的回车标识，在Linux环境下就会出现不兼容的问题。

##### 解决方法：

> 1.只需要把^M的标志符删除，该脚本文件即可正常执行。不过这种方法只适用于少量文本，如果是大量的脚本代码，这显然是不适用的。
>
>2.通过命令的方式，将shell文件的格式改为unix。

```shell
vim hello.sh
:set fileformat=unix
:x
```

> 使用vim编辑文本的时候，不要使用-b参数，否则是无法将shell文件的文件格式修改为unix的。





