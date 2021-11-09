FROM node:16-alpine 

RUN sed -i 's/dl-cdn.alpinelinux.org/mirrors.ustc.edu.cn/g' /etc/apk/repositories && \
  apk add --no-cache make gcc g++ python3 git

