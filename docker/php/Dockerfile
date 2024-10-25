FROM php:8.3-fpm

# Install required libs
RUN apt-get update && ACCEPT_EULA=Y apt-get install -y libzip-dev unzip libpng-dev

# Install php extensions
RUN printf "\n" | pecl install redis
RUN docker-php-ext-enable redis
RUN docker-php-ext-install pdo_mysql bcmath zip gd opcache

# Custom configurations
COPY ./templates/php.conf /usr/local/etc/php-fpm.d/zzz-custom.conf

# Install composer
RUN curl -sS https://getcomposer.org/installer | php -- --filename=composer --install-dir=/usr/local/bin

# Change workdir
WORKDIR /var/www

CMD ["php-fpm"]
