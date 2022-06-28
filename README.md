## Heimdall-汉化


***
### 直接运行以下命令，直接就是就带了中文：

```
docker run -d \
  --name=heimdall \
  -e TZ="Asia/Shanghai" \
  -p 8888:80 \
  -p 8899:443 \
  -v /root/heimdall/config:/config \
  --restart unless-stopped \
  lscr.io/linuxserver/heimdall:latest
```

8888为http访问端口(可自行修改)

8899为https访问端口(可自行修改)


***







### 汉化步骤(以下步骤不用看了)

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
