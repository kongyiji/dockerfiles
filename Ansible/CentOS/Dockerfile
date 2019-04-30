FROM centos
MAINTAINER Kong Yiji

# set time zone to Shanghai
ENV TIME_ZONE Asia/Shanghai
RUN cp /usr/share/zoneinfo/${TIME_ZONE} /etc/localtime

# install ansible
# needed: epel and pip
RUN yum install -y epel-release
RUN yum install -y python-pip
RUN pip install -i https://pypi.tuna.tsinghua.edu.cn/simple ansible