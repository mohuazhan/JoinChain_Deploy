FROM python:3.7
ENV REFRESHED_AT 2020-08-10
ENV PATH /usr/local/bin:$PATH

#add the scrapyd configure file
ADD ./scrapyd.conf /etc/scrapyd/scrapyd.conf

#add requirements.txt
ADD requirements.txt /opt/requirements.txt
WORKDIR /opt

# 设置时区
RUN cp /usr/share/zoneinfo/Asia/Shanghai /etc/localtime && echo 'Asia/Shanghai'>/etc/timezone
# install scrapyd
RUN pip3 install  -i https://pypi.tuna.tsinghua.edu.cn/simple -r requirements.txt
# install logparser
RUN pip3 install  -i https://pypi.tuna.tsinghua.edu.cn/simple logparser
# install supervisor
RUN pip3 install  -i https://pypi.tuna.tsinghua.edu.cn/simple supervisor
# 拷贝配置文件
COPY supervisord.conf /etc/supervisor/

#设置容器启动时执行的命令
# ENTRYPOINT ["/usr/bin/supervisord", "-nc", "/etc/supervisor/supervisord.conf"]
ENTRYPOINT ["supervisord", "-nc", "/etc/supervisor/supervisord.conf"]

EXPOSE 6800