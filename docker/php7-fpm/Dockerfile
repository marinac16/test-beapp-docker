# See https://github.com/docker-library/php/blob/4677ca134fe48d20c820a19becb99198824d78e3/7.0/fpm/Dockerfile
FROM php:7.1-fpm

MAINTAINER Maxence POUTORD <maxence.poutord@gmail.com>

RUN apt-get update && apt-get install -y \
    git \
    unzip \
    zlib1g-dev \
    libpq-dev

# Install Composer
RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer
RUN composer --version
RUN mkdir /var/www/.composer && chown -R www-data /var/www/.composer

# Set timezone
RUN rm /etc/localtime
RUN ln -s /usr/share/zoneinfo/Europe/Paris /etc/localtime
RUN "date"

# Type docker-php-ext-install to see available extensions
RUN docker-php-ext-install pdo pdo_pgsql zip



RUN echo 'alias sf3="php bin/console"' >> ~/.bashrc

RUN usermod -u 1000 www-data

WORKDIR /var/www/symfony