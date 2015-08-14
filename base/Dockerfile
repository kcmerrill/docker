FROM ubuntu
RUN apt-get update && apt-get install -y vim php5 php5-mongo curl php5-curl ssmtp
RUN rm -rf /var/www
RUN mkdir -p /var/www/html
WORKDIR /var/www/html
COPY apache2.conf /etc/apache2/sites-available/001-custom.conf
RUN a2enmod rewrite
RUN ln -s /etc/apache2/sites-available/001-custom.conf /etc/apache2/sites-enabled/001-custom.conf
RUN unlink /etc/apache2/sites-enabled/000-default.conf
COPY ssmtp.conf /etc/ssmtp/ssmtp.conf
EXPOSE 80
ENTRYPOINT /usr/sbin/apache2ctl -D FOREGROUND
