FROM openjdk:8-jre-alpine

ENV TZ=Asia/Shanghai

RUN ln -snf /usr/share/zoneinfo/$TZ /etc/localtime && echo $TZ > /etc/timezone

RUN echo -e "https://mirror.tuna.tsinghua.edu.cn/alpine/v3.4/main\n\
https://mirror.tuna.tsinghua.edu.cn/alpine/v3.4/community" > /etc/apk/repositories

RUN apk --update add curl bash ttf-dejavu && \
      rm -rf /var/cache/apk/*

# 拷贝应用
ADD canal.tar.gz /

#应用需要暴露的端口
EXPOSE 8081

ENTRYPOINT ["tail","-f","/dev/null"]
