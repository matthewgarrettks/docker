FROM php:8.0-alpine

RUN apk add --no-cache wget autoconf gcc g++ make sed icu-dev 
RUN apk add --update linux-headers

RUN docker-php-ext-configure intl && docker-php-ext-install intl
RUN pecl channel-update pecl.php.net && pecl install xdebug-3.2.1

COPY ./php.ini /usr/local/etc/php/php.ini
COPY ./keeprunning.sh /keeprunning.sh

RUN chmod 700 /keeprunning.sh

CMD ["/keeprunning.sh"]
