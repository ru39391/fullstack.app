FROM php:8.2-fpm

RUN apt update && apt-get install -y \
    libzip-dev \
    libpng-dev \
    libjpeg62-turbo-dev \
    zip \
    && apt-get clean \
    && rm -rf /var/lib/apt/lists/*

RUN docker-php-ext-install \
    gd \
    zip \
    curl \
    intl \
    mbstring \
    mysqlnd \
    mysqli \
    opcache \
    pdo \
    pdo_mysql \
    session \
    tokenizer \
    dom \
    json \
    xml \
    xmlreader \
    xmlwriter \
    simplexml

RUN echo "memory_limit=256M" > /usr/local/etc/php/conf.d/custom.ini \
    && echo "upload_max_filesize=64M" >> /usr/local/etc/php/conf.d/custom.ini