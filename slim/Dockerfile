FROM node:16-alpine 
RUN sed -i 's/dl-cdn.alpinelinux.org/mirrors.ustc.edu.cn/g' /etc/apk/repositories && \
  apk add --no-cache binutils && \
  strip /usr/local/bin/node && \
  apk del binutils


FROM alpine:3.14
COPY --from=0 /usr/local/bin/node /usr/bin/
RUN sed -i 's/dl-cdn.alpinelinux.org/mirrors.ustc.edu.cn/g' /etc/apk/repositories && \
  apk add --no-cache libstdc++