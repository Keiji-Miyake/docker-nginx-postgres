FROM php:7.3-fpm

ENV TZ Asia/Tokyo
ENV COMPOSER_ALLOW_SUPERUSER 1

# install Lib
RUN apt-get update -qq && \
    apt-get install --no-install-recommends -y \
                libpq-dev \
                git zip unzip && \
    pecl install xdebug && \
    rm -rf /var/cache/apt && \
    docker-php-ext-install mbstring pdo pdo_pgsql && \
    pecl install -o -f redis && \
    rm -rf /tmp/pear && \
    docker-php-ext-enable redis xdebug

# install Composer
RUN curl -sS https://getcomposer.org/installer | php && \
    mv composer.phar /usr/local/bin/composer && \
    chmod +x /usr/local/bin/composer