# 安装部署手册

- windows用户参考: [windows-install.md](windows-install.md)
- linux用户参考: [linux-install.md](linux-install.md)
- mac用户参考: [mac-install.md](mac-install.md)

# 镜像下载

通过docker官方镜像站下载(pull)比较慢, 可以通过百度云下载离线镜像进行加载:

- 下载镜像

链接: https://pan.baidu.com/s/13Ki4OU7XHaVPoAxj-8gLZA 提取码: 9asb

- 加载镜像

对下载好的镜像进行加载
```bash
docker load -i writer-assistant-server.tar
```

- 启动镜像

```bash
docker run -d -p 23423:80 --name writer-assistant-server mymusise/writer-assistant-server
```
