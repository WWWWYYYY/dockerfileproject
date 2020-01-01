FROM openjdk:8-jre-alpine

#构建时只能找到当前文件所在的位置
ADD *.war app.war

RUN sh -c 'touch /app.war'

RUN ln -sf /usr/share/zoneinfo/Asia/Shanghai /etc/localtime && echo 'Asia/Shanghai' >/etc/timezone

EXPOSE 8761 8861  5701/udp

ENTRYPOINT ["java","-Djava.security.egd=file:/dev/./urandom","-agentlib:jdwp=transport=dt_socket,server=y,suspend=n,address=8861","-jar","/app.war"]
