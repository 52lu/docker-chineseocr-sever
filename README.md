# 1.介绍
基于[chineseocr_lite](https://github.com/DayBreak-u/chineseocr_lite)，使用docker-compose快速搭建ocr服务，免去部署难题，项目中对身份证OCR识别进行了简单的二次开发，身份证照片最好是横着上传，对竖着上传身份证识别度不好；

# 2.目录结构
```
├── README.md
├── chineseocr
|   ├── Dockerfile
|   └── init.sh
└── docker-compose.yml
```

# 3.获取项目代码
```
# 切到chineseorc目录
$ cd chineseorc

# 默认分支，即 main
$ git clone https://github.com/52lu/chinese-ocr-lite.git

# 克隆后代码目录展示
├── README.md
├── chineseocr
|   ├── Dockerfile
|   ├── chineseocr_lite
|   └── init.sh
└── docker-compose.yml
```



# 4.启动服务
```
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