FROM php:fpm-alpine

RUN apk --update --no-cache add git
RUN apk add --update nodejs npm yarn
RUN docker-php-ext-install pdo_mysql opcache

COPY --from=composer /usr/bin/composer /usr/bin/composer

WORKDIR /var/www

CMD composer install ; yarn encore dev ;  php-fpm

EXPOSE 9000
