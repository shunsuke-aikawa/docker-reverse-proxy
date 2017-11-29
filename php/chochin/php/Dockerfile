FROM php:7-fpm

RUN apt-get update && apt-get install -y libmcrypt-dev mysql-client \
    && docker-php-ext-install mcrypt pdo_mysql && \

    #zip,unzip
    apt-get install -y zip unzip && \

    #vim
    apt-get install -y vim && \

    #git
    apt-get install -y git && \

    #composer
    curl -sS https://getcomposer.org/installer | php && \
    mv composer.phar /usr/local/bin/composer && \

    #user追加
    useradd -m -s /bin/bash -u 1000 appcapsule && \

    #www.conf修正
    sed -i 's/user\ \=\ www-data/user\ \=\ appcapsule/g' /usr/local/etc/php-fpm.d/www.conf && \
    sed -i 's/group\ \=\ www-data/group\ \=\ appcapsule/g' /usr/local/etc/php-fpm.d/www.conf

WORKDIR /var/ac2

