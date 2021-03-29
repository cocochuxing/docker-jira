FROM cptactionhank/atlassian-confluence:6.13.0

USER root

# 将代理破解包加入容器
COPY "atlassian-agent.jar" /opt/atlassian/confluence/
COPY "server.xml" /opt/atlassian/confluence/conf
RUN mv /opt/atlassian/confluence/confluence/WEB-INF/lib/mail-1.4.5.jar /opt/atlassian/confluence/lib/mail-1.4.5.jar
RUN mkdir /home/confluence
RUN chmod -R 777 /home/confluence
RUN chmod -R 777 /var/atlassian/

# 设置启动加载代理包
RUN echo 'export CATALINA_OPTS="-javaagent:/opt/atlassian/confluence/atlassian-agent.jar ${CATALINA_OPTS}"' >> /opt/atlassian/confluence/bin/setenv.sh