FROM kcmerrill/buildtools

RUN mkdir -p /wd/code
COPY composer.json /wd/composer.json
RUN cd /wd/ && composer install
WORKDIR /wd/code
ENTRYPOINT phpunit
