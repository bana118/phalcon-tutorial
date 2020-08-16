FROM ubuntu:18.04

# avoid freeze while configuring tzdata
ENV DEBIAN_FRONTEND=noninteractive

#Author
MAINTAINER banatech

CMD echo "now running..."

RUN apt update \
    && apt install -y --no-install-recommends \
    apt-utils \
    curl \
    git \
    gcc \
    nano \
    vim-nox \
    build-essential \
    apache2 \
    nginx \
    zip \
    php \
    php-zip \
    php-xml \
    php-fpm \
    php-dev \
    php-curl \
    php-gettext \
    php-gd \
    php-imagick \
    php-json \
    php-sqlite3 \
    php-mysql \
    php-memcached \
    libpcre3-dev \
    composer \
    sqlite3 \
    && echo "extension=psr.so" >> /etc/php/7.2/cli/php.ini \
    && echo "extension=phalcon.so" >> /etc/php/7.2/cli/php.ini \
    && echo "extension=psr.so" >> /etc/php/7.2/apache2/php.ini \
    && echo "extension=phalcon.so" >> /etc/php/7.2/apache2/php.ini \
    && echo "extension=psr.so" >> /etc/php/7.2/fpm/php.ini \
    && echo "extension=phalcon.so" >> /etc/php/7.2/fpm/php.ini \
    && pecl channel-update pecl.php.net \
    && pecl install phalcon \
    && composer global require phalcon/devtools \
    && apt autoremove -y \
    && apt clean -y \
    && rm -rf /var/lib/apt/lists/*

ENV PATH $PATH:$HOME/.composer/vendor/bin
