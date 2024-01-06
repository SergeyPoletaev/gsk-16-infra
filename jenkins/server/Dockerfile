# Сборка сервера Jenkins
FROM jenkins/jenkins:2.375.4-jdk11
COPY jenkins_plugins.txt /tmp/jenkins_plugins.txt
RUN jenkins-plugin-cli -f /tmp/jenkins_plugins.txt
USER root
RUN rm /tmp/jenkins_plugins.txt
RUN cat /etc/group
# номер группы docker на хосте 
# проверить на хосте и вставить свое число: grep -w ^docker /etc/group
RUN groupadd -g 998 docker
RUN usermod -aG docker jenkins
USER jenkins
