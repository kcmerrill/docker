FROM ubuntu

RUN apt-get update && apt-get install -y fontforge ttfautohint nodejs php5 curl wget hostname npm curl

RUN ln -s `which nodejs` /usr/bin/node

RUN npm install -g gulp
RUN npm install -g bower
RUN npm install -g grunt-cli

RUN echo "{ \"allow_root\":  true, \"interactive\": false }" >> /.bowerrc

RUN cd /usr/local/bin && php -r "readfile('https://getcomposer.org/installer');" | php
RUN mv /usr/local/bin/composer.phar /usr/local/bin/composer

RUN composer global require "phpunit/phpunit=4.8.*"

RUN echo "export PATH=~/.composer/vendor/bin/:$PATH" >> ~/.bashrc

RUN ln -s ~/.composer/vendor/bin/phpunit /usr/local/bin/phpunit

CMD ["phpunit"]
