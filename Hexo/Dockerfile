FROM node:10.15.3
MAINTAINER Kong Yiji

# In China, use cnpm instead of npm
RUN npm install -g cnpm --registry=https://registry.npm.taobao.org
# install hexo
RUN cnpm install hexo-cli -g

WORKDIR /myblog