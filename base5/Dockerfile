FROM ubuntu:14.04
RUN apt-get update && apt-get install -y vim php5 curl php5-curl git ssmtp libapache2-modsecurity apache2 php5-mysql php5-mcrypt libapache2-mod-php5
RUN rm -rf /var/www
RUN mkdir -p /var/www/html
WORKDIR /var/www/html
COPY apache2.conf /etc/apache2/sites-available/001-custom.conf
RUN a2enmod rewrite
RUN ln -s /etc/apache2/sites-available/001-custom.conf /etc/apache2/sites-enabled/001-custom.conf
RUN unlink /etc/apache2/sites-enabled/000-default.conf
COPY ssmtp.conf /etc/ssmtp/ssmtp.conf
COPY conf/php/ /etc/php5/cli/conf.d/
COPY conf/php/ /etc/php5/apache2/conf.d/
RUN a2enmod headers
RUN php5enmod mcrypt
RUN echo "<?php phpinfo();" >> /var/www/phpinfo.php
RUN apt-get install -y php5-gd
EXPOSE 80
ENTRYPOINT /usr/sbin/apache2ctl -D FOREGROUND
