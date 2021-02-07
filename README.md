# Writer Assistant

一款基于生成模型GPT-2的写作助手，旨在提高写作速度和增加写作灵感。目前依托vscode平台，作为插件辅助用户写作使用。

## 效果

![](https://github.com/mymusise/vscode-writer-assistant/raw/main/images/demo.gif)

## 使用

打开需要编辑的TXT文件， 编辑一个开头后，追加一个空格符 `_` ， 然后按 `Ctrl` + `I` 补全句子。例如： 输入”今天... 我们“上文后，需要在后面追加一个空格”今天... 我们 <span> </span>“，才能进行补全。

> 注意：打开的文本后缀必须是.txt, 新建的文本需要保存后才能自动补全。

## 安装

### 插件安装

通过[vscode市场](https://marketplace.visualstudio.com/items?itemName=mymusise.writer-assistant)搜索 `writer-assistant` 可以直接安装插件, 也可以通过[下载插件](https://github.com/mymusise/vscode-writer-assistant/releases/download/v0.1/writer-assistant-0.1.0.vsix)进行手动安装。

插件默认的服务是在线的，目前跑在一台只有两核的服务器上T^T，所有有时候请求会比较慢，如果想提高性能，可以通过本地部署服务来提升体验。

### 本地部署服务

通过本地部署服务和配置

* 可以提高服务的响应速度，当然这个也取决于本地机器的性能。
* 本地部署还可以突破补全字数以及推荐的句子数的限制。

#### **Docker环境安装**

服务运行需要Docker环境，如果你的机器没有Docker, 下载安装参考[官网](https://docs.docker.com/get-docker/)

#### **启动服务**

已经打包成镜像，可以直接pull下来运行。

``` bash
docker run -d -p 23423:80 --name writer-assistant-server mymusise/writer-assistant-server
```

更具体的安装过程参考[详细文档](docs/README.md)

## 设置参数

* `serverAddress`: 后台服务地址，本地部署后填写本地地址
* `maxContext`: 最大参考上下文长度（只参考上文）
* `maxLength`: 生成文本的最大长度（通用服务最长长度为8, 本地部署最长支持128）
* `numSuggest`: 推荐的句子数（通用服务一次最多推荐3个句子, 本地部署不受限制）

![图](https://github.com/mymusise/vscode-writer-assistant/raw/main/images/settings.jpeg)

### 声明

项目用到的数据均来源网络，本项目未进行任何商业目的。本项目遵从[GPL协议](LICENSE)，引用请注明出处。
