FROM python:3.6

LABEL Author="Pad0y<github.com/Pad0y>"

ENV LANG C.UTF-8 LC_ALL=C.UTF-8

# 时区
RUN ln -snf /usr/share/zoneinfo/PRC /etc/localtime && echo PRC > /etc/timezone

# 拷贝目录
COPY ./init.sh /data/init.sh
ADD ./chineseocr_lite /data/chineseocr_lite

# 切换目录
WORKDIR /data/chineseocr_lite


# 安装依赖
RUN pip3 install --user  -U pip -i https://pypi.tuna.tsinghua.edu.cn/simple/
RUN pip3 config set global.index-url https://mirrors.aliyun.com/pypi/simple/
RUN pip3 install -r requirements.txt



