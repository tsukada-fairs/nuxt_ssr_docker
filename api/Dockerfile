FROM php:7.4-fpm-alpine
COPY api/php.ini /usr/local/etc/php/
COPY api/start.sh /var/www/
RUN chmod 744 /var/www/start.sh
 
WORKDIR /var/www/html
 
RUN apk --no-cache update && \
    apk --no-cache upgrade && \
    apk --no-cache add \
    freetype-dev libjpeg-turbo-dev libpng-dev libxml2-dev \
    git vim unzip tzdata \
    zlib-dev pcre-dev curl-dev oniguruma-dev\
    && docker-php-ext-install pdo_mysql mysqli mbstring gd iconv \
    && docker-php-ext-enable mysqli \
    # timezoneをAsia/Tokyoに設定する
    && cp /usr/share/zoneinfo/Asia/Tokyo /etc/localtime \
    && apk del tzdata \
    && rm -rf /var/cache/apk/*
 
RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer
 
ENV TZ=Asia/Tokyo
 
EXPOSE 8000
 
CMD ["../start.sh"]