# 1.介绍
基于[chineseocr_lite](https://github.com/DayBreak-u/chineseocr_lite)快速搭建ocr服务，按照步骤即可直接部署使用，项目中对身份证OCR识别进行了简单的二次开发，身份证上传需要(横着)，对竖着上传支持度不好；

# 2.目录结构
```
│  .gitignore
│  docker-compose.yml
│  readme.md
├─chineseorc
│      init.sh
```
其中`.docker`目录不是必须的，是配合docker-desktop一起用的，一个python的开发环境

其中`docker-compose.yml`文件中`networks`的定义，为了与其他`docker-compose.yml`网络互通，使用了外部网络。如果不需要多个docker-compose互通，可以修改一下
```
version: '3'
networks:
  web-network:

services:
  ocr-server:
    ...
    networks:
      - web-network
```
# 3.获取项目代码
```
cd chineseorc
#默认分支，即 main
git clone git@github.com:52lu/chinese-ocr-lite.git
```



# 4.启动服务
```
# 创建网络
docker network create web-network

# 启动
docker-compose up -d
```

![image-20230423185804965](https://s2.loli.net/2023/04/23/BW71KAEkzCZGoId.png)

# 5.请求
## 5.1 浏览器访问
访问： http://127.0.0.1:8089/


## 5.2 接口请求
```shell
POST http://127.0.0.1:8089/api/tr-run/
# 参数
- file: 上传文件
- ocr_type: 1 (身份证)
```

# 5.二次开发(身份证ocr)

![image-20230423185944647](https://s2.loli.net/2023/04/23/c8CYg2GtIoFQhxK.png)