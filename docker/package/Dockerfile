# original https://hub.docker.com/r/bwits/rundeck-build/
FROM centos:6
MAINTAINER Bill W
RUN rpm -Uvh  http://dl.fedoraproject.org/pub/epel/6/x86_64/epel-release-6-8.noarch.rpm
RUN yum -y update
RUN yum -y install java-1.8.0-openjdk java-1.8.0-openjdk-devel git rpm-build unzip fakeroot dpkg
RUN yum -y install wget zip
RUN wget https://bintray.com/artifact/download/groovy/maven/groovy-binary-2.4.11.zip
RUN unzip groovy-binary-2.4.11.zip
RUN rm groovy-binary-2.4.11.zip
RUN useradd rundeck
USER rundeck
VOLUME ["/home/rundeck/rundeck"]
#RUN git clone https://github.com/rundeck/rundeck.git /home/rundeck/rundeck
ENV JAVA_HOME=/etc/alternatives/java_sdk
ENV GROOVY_HOME=/groovy-2.4.11
ENV PATH=$PATH:$GROOVY_HOME/bin
WORKDIR /home/rundeck/rundeck