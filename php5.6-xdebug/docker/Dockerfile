FROM php:5.6.40-alpine

RUN apk add --no-cache wget autoconf gcc g++ make sed icu-dev 
RUN docker-php-ext-configure intl && docker-php-ext-install intl
RUN pecl channel-update pecl.php.net && pecl install xdebug-2.5.5

COPY ./php.ini /usr/local/etc/php.ini
COPY ./php.ini /usr/local/etc/php/conf.d/docker-php-ext-intl.ini
COPY ./keeprunning.sh /keeprunning.sh

RUN chmod 700 /keeprunning.sh

CMD ["/keeprunning.sh"]
