FROM kcmerrill/base
RUN apt-get update && apt-get install -y wget unzip
WORKDIR /tmp
RUN wget https://getgrav.org/download/core/grav-admin/latest
RUN unzip latest
RUN cp -r /tmp/grav-admin/* /var/www/html/.
