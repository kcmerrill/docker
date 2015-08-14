FROM centos:centos7
RUN yum update -y
RUN yum -y install firefox Xvfb wget php php-xml
RUN wget -O /opt/selenium-server.jar http://selenium-release.storage.googleapis.com/2.45/selenium-server-standalone-2.45.0.jar
RUN chmod 755 /opt/selenium-server.jar
RUN yum -y install java-1.7.0-openjdk.x86_64
RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer
ADD . /seleniumwd
RUN mkdir -p /seleniumwd/code
EXPOSE 4449
EXPOSE 4444
WORKDIR /seleniumwd
RUN composer install
ENTRYPOINT xvfb-run -a -s "-screen 0 1280x1600x24 -noreset" java -jar selenium-server-standalone.jar -role node
