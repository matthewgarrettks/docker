FROM php:7.0-alpine

RUN apk add --no-cache wget autoconf gcc g++ make sed icu-dev 
RUN apk add --update linux-headers

RUN docker-php-ext-configure intl && docker-php-ext-install intl
RUN pecl channel-update pecl.php.net && pecl install xdebug-2.4.1

COPY ./php.ini /usr/local/etc/php.ini
COPY ./php.ini /usr/local/etc/php/conf.d/docker-php-ext-intl.ini
COPY ./keeprunning.sh /keeprunning.sh

RUN chmod 700 /keeprunning.sh

CMD ["/keeprunning.sh"]
