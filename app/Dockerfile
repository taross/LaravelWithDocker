FROM php:7-fpm

RUN apt-get update && apt-get install -y libmcrypt-dev mysql-client \
    && docker-php-ext-install mcrypt pdo_mysql && \

    #zip,unzip
    apt-get install -y zip unzip && \

    #vim
    apt-get install -y vim && \

    #composer
    curl -sS https://getcomposer.org/installer | php && \
    mv composer.phar /usr/local/bin/composer && \

    #user追加
    useradd -m -s /bin/bash -u 1000 taross && \

    #権限、user切り替え
    chown -R taross:taross /var/www && \
    su taross && \

    #www.conf修正
    sed -i 's/user\ \=\ www-data/user\ \=\ taross/g' /usr/local/etc/php-fpm.d/www.conf && \
    sed -i 's/group\ \=\ www-data/group\ \=\ taross/g' /usr/local/etc/php-fpm.d/www.conf
WORKDIR /var/www
