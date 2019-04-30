FROM python:3.7.3-alpine3.9
MAINTAINER Kong Yiji

# set time zone to Shanghai
ENV TIME_ZONE Asia/Shanghai

RUN apk add -U --no-cache tzdata \
&& cp /usr/share/zoneinfo/${TIME_ZONE} /etc/localtime \
&& echo "${TIME_ZONE}" > /etc/timezone

# install ansible
RUN apk add -U --no-cache build-base libffi-dev openssl-dev \
&& pip install -i https://pypi.tuna.tsinghua.edu.cn/simple ansible