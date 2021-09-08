## Heimdall-汉化

### 汉化步骤

#### 先安装heimdall：

```
docker run -d \
  --name=heimdall \
  -e TZ="Asia/Shanghai" \
  -p 8888:80 \
  -p 8899:443 \
  -v /root/heimdall/config:/config \
  -v /root/heimdall/data:/data \
  -v /root/heimdall/lang:/var/www/localhost/heimdall/resources/lang \
  -v /root/heimdall/app:/var/www/localhost/heimdall/app \
  --restart unless-stopped \
  linuxserver/heimdall
```
我是把heimdall的语言包、配置等直接映射到/root/heimdall文件夹下

8888为http访问端口(可自行修改)

8899为https访问端口(可自行修改)

#### 再汉化和修改搜索：

把本项目的app下的文件替换到/root/heimdall/app下

把本项目的lang/en下的文件替换到/root/heimdall/lang/en下

搜索修改到只有3个：谷歌、Bing、百度

替换完成后，刷新下就变中文了~

### 使用项目

[linuxserver/heimdall](linuxserver/heimdall)

[Heimdall 大中华镜像源(修改版)](https://gitee.com/sKai-Zhang/Heimdall-List/tree/master)

[土味汉化文件地址](https://pan.baidu.com/s/1OQwK8oY3Q7ZmW4r4eQ-QiQ) 提取码：ijf5

[odyf/heimdall-cn](https://github.com/odyf/heimdall-cn)

汉化原理：heimdall采用了专门的语言包，找到这个语言包，加上自己的翻译，然后替换即可。

