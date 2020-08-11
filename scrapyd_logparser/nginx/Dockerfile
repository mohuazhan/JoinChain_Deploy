FROM nginx

# 使用RUN命令设置时区
RUN cp /usr/share/zoneinfo/Asia/Shanghai /etc/localtime && echo 'Asia/Shanghai'>/etc/timezone

ADD default.conf /etc/nginx/conf.d/
ADD passwd /etc/nginx/
