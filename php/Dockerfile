FROM php:8.2-fpm

RUN apt-get update && apt-get install -y \
    # json 
    libjson-c-dev \
    # XML расширения (xml, dom, simplexml, xmlreader, xmlwriter)
    libxml2-dev \
    libxslt-dev \
    # MBString (многобайтовые строки)
    libonig-dev \
    # Zip расширение
    libzip-dev \
    # GD (работа с изображениями)
    libpng-dev \
    libjpeg62-turbo-dev \
    libfreetype6-dev \
    # Intl (интернационализация)
    libicu-dev \
    zip \
    unzip

RUN docker-php-ext-install \
    mysqli pdo pdo_mysql \
    xml dom simplexml \
    mbstring intl opcache \
    session zip
# RUN docker-php-ext-install json xmlreader xmlwriter tokenizer

RUN docker-php-ext-configure gd --with-jpeg --with-freetype
RUN docker-php-ext-install gd

RUN echo "memory_limit=256M" > /usr/local/etc/php/conf.d/custom.ini \
    && echo "upload_max_filesize=64M" >> /usr/local/etc/php/conf.d/custom.ini

RUN apt-get clean && rm -rf /var/lib/apt/lists/*