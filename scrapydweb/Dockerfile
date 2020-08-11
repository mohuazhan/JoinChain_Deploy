FROM python:3.7

# 设置时区
RUN cp /usr/share/zoneinfo/Asia/Shanghai /etc/localtime && echo 'Asia/Shanghai'>/etc/timezone
# install scrapydweb
RUN pip3 install  -i https://pypi.tuna.tsinghua.edu.cn/simple scrapydweb

COPY . /opt

WORKDIR /opt

CMD scrapydweb

EXPOSE 5050