FROM ubuntu
RUN apt-get update && apt-get install -y vim php7.0 curl php7.0-curl git ssmtp libapache2-modsecurity apache2
RUN mv /etc/modsecurity/modsecurity.conf-recommended /etc/modsecurity/modsecurity.conf
RUN sed -i -e 's/SecRuleEngine DetectionOnly/SecRuleEngine on/g' /etc/modsecurity/modsecurity.conf
RUN cp /usr/share/modsecurity-crs/base_rules/* /usr/share/modsecurity-crs/activated_rules/.
RUN cp /usr/share/modsecurity-crs/optional_rules/* /usr/share/modsecurity-crs/activated_rules/.
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
RUN curl -sSL https://get.docker.com/ | sh
RUN a2enmod headers
EXPOSE 80
ENTRYPOINT /usr/sbin/apache2ctl -D FOREGROUND
