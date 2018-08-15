#指Docker Hub上官方提供的java镜像
FROM java
#创建/tmp目录并持久化到Docker数据文件夹，因为Spring Boot使用的内嵌Tomcat容器默认使用/tmp作为工作目录
VOLUME /tmp
VOLUME /eureka-service/lib
#将应用jar包复制到/eureka-service.jar
ADD ./eureka-service-0.0.1-SNAPSHOT.jar /eureka-service/eureka-service.jar
ADD ./lib /eureka-service/lib/
RUN bash -c 'touch /eureka-service/eureka-service.jar'
ENV JAVA_OPTS=""
#对外的端口 
EXPOSE 9999
#表示容器运行后默认执行的命令
ENTRYPOINT [ "sh", "-c", "java $JAVA_OPTS -Djava.security.egd=file:/dev/./urandom -jar /eureka-service/eureka-service.jar" ]