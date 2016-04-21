FROM ubuntu:14.04.4
MAINTAINER kcmerrill@gmail.com

RUN apt-get update \
    && apt-get install -y wget vim curl software-properties-common python-software-properties \
    && apt-get clean

RUN add-apt-repository ppa:webupd8team/java
RUN apt-get update

#Yeah yeah yeah ... we accept your license.
RUN echo oracle-java7-installer shared/accepted-oracle-license-v1-1 select true | /usr/bin/debconf-set-selections
RUN apt-get install -y oracle-java7-installer

#BEEEEEEEELINE
RUN wget -O - http://package.mapr.com/releases/pub/maprgpg.key | sudo apt-key add -
RUN echo "deb http://package.mapr.com/releases/v5.0.0/ubuntu/ mapr optional" >> /etc/apt/sources.list
RUN echo "deb http://package.mapr.com/releases/ecosystem-5.x/ubuntu binary/" >> /etc/apt/sources.list
RUN apt-get update && apt-get install -y --force-yes mapr-hive=0.13.201604062232 && apt-get clean

ENTRYPOINT whoami
