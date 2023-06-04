FROM php:fpm-alpine as php
EXPOSE 9000
#WORKDIR /usr/src/myapp

RUN apk update && apk add --no-cache \
    curl \
    && rm -rf /var/cache/apk/*

HEALTHCHECK --interval=30s --timeout=30s --start-period=5s --retries=3 \
    CMD  ["curl localhost:9000"]

CMD ["php-fpm"]





# COPY php-fpm.conf /usr/local/etc/php-fpm.conf
# COPY www.conf /usr/local/etc/php-fpm.d/www.conf

# CMD [ "php", "./index.php" ] 