from php:5.5-fpm

RUN apt-get update
RUN apt-get install -y libwebp-dev libjpeg62-turbo-dev libpng-dev libxpm-dev \
  libfreetype6-dev zlib1g-dev libzip-dev curl libcurl4-gnutls-dev


RUN docker-php-ext-install mysqli pdo pdo_mysql curl


RUN docker-php-ext-install mbstring


RUN docker-php-ext-install zip

RUN apt-get install -y zlib1g-dev libicu-dev g++ \
&& docker-php-ext-configure intl \
&& docker-php-ext-install intl

RUN apt install -y iputils-ping

RUN pecl install mailparse-2.1.6 \
&& docker-php-ext-enable mailparse

RUN apt-get update && apt-get install -y libc-client-dev libkrb5-dev && rm -r /var/lib/apt/lists/*
RUN docker-php-ext-configure imap --with-kerberos --with-imap-ssl \
    && docker-php-ext-install imap

RUN apt update && apt install php5-dev -y

RUN pecl install redis-2.2.8

RUN docker-php-ext-enable redis



CMD ["php-fpm"]

EXPOSE 9000