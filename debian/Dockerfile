FROM debian:buster
# this is ant image created for working with codeql
RUN apt-get update \
    && apt-get install -y wget
RUN mkdir -p /opt/ant
#Download Ant 1.9.8
RUN wget http://archive.apache.org/dist/ant/binaries/apache-ant-1.10.3-bin.tar.gz
#Unpack Ant
RUN tar -xvzf apache-ant-1.10.3-bin.tar.gz -C /opt/ant/
# Remove tar file
RUN rm -f apache-ant-1.10.3-bin.tar.gz
#Drop Sonarqube lib
# RUN wget http://downloads.sonarsource.com/plugins/org/codehaus/sonar-plugins/sonar-ant-task/2.3/sonar-ant-task-2.3.jar -P /opt/ant/apache-ant-1.9.8/lib/
#Install JDK 1.8
RUN apt-get install -y default-jdk

#Setting Ant Home
ENV ANT_HOME=/opt/ant/apache-ant-1.10.3
#Setting Ant Params
ENV ANT_OPTS="-Xms256M -Xmx512M"
#Updating Path
ENV PATH="${PATH}:${HOME}/bin:${ANT_HOME}/bin"