FROM inutano/wget:latest AS downloader

RUN wget -q https://raw.githubusercontent.com/winewei/tools/master/jdk1.8.0_181.tar.gz --no-check-certificate
RUN tar xf jdk1.8.0_181.tar.gz

FROM debian:stretch-slim

COPY --from=downloader /jdk1.8.0_181 /usr/local/jdk1.8.0_181

ENV JAVA_HOME=/usr/local/jdk1.8.0_181 \
    JRE_HOME=/usr/local/jdk1.8.0_181/jre \
    PATH=.:/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/usr/local/jdk1.8.0_181/bin
RUN cp /usr/share/zoneinfo/Hongkong /etc/localtime
