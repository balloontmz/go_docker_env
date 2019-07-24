FROM alpine:latest

RUN mkdir /lib64 && ln -s /lib/libc.musl-x86_64.so.1 /lib64/ld-linux-x86-64.so.2

RUN apk upgrade && apk add --no-cache ca-certificates

RUN mkdir /loupdag

WORKDIR /var/html

# 采用环境中的 配置端口导出
EXPOSE ${CONFIG_PORT}

# 采用配置文件运行程序
ENTRYPOINT ["./worldmap-api", "b", "-c", "config.ini"]