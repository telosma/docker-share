FROM php:5.6-apache
# ref: https://github.com/docker-library/php/blob/c77c579341cfbfee90e669535ea3057679a1005b/5.6/stretch/apache/Dockerfile
RUN apt-get update && apt-get install -y \
    vim \
    libpq-dev \
    libmcrypt-dev  \
    libreadline-dev \
    curl \
    libpng-dev
RUN /usr/local/bin/docker-php-ext-install \
    pdo \
    pdo_mysql \
    pdo_pgsql \
    mysql \
    mysqli \
    pgsql \
    mcrypt \
    gd \
    json \
    mbstring \
    mcrypt

RUN /usr/local/bin/docker-php-ext-enable \
    pdo \
    pdo_mysql \
    pdo_pgsql \
    mysql \
    mysqli \
    pgsql \
    mcrypt \
    gd \
    json \
    mbstring \
    mcrypt
RUN a2enmod rewrite
RUN a2enmod include
COPY apache2-foreground /usr/local/bin/
RUN chmod +x /usr/local/bin/apache2-foreground
WORKDIR /var/www

EXPOSE 80
CMD ["apache2-foreground"]
