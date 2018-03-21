FROM jenkinsci/jenkins:alpine
MAINTAINER tkrplus

COPY plugins.txt /usr/share/jenkins/plugins.txt
RUN /usr/local/bin/plugins.sh /usr/share/jenkins/plugins.txt

USER jenkins
