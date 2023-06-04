FROM nginx:1.23.4-alpine as nginx

WORKDIR /var/www/html/

ARG VERSION

RUN apk add --no-cache \
    curl \
    && rm -rf /var/cache/apk/*

LABEL org.opencontainers.image.version="$VERSION"
LABEL org.opencontainers.image.authors="Wojciech Dziedzic"

#COPY default.conf /etc/nginx/conf.d/default.conf 
#COPY ../data/index.php /usr/share/nginx/html/index.php

VOLUME [ "/data" ]

EXPOSE 6002

HEALTHCHECK --interval=30s --timeout=30s --start-period=5s --retries=3 \
    CMD [ "curl localhost:6002" ]

CMD ["nginx", "-g", "daemon off;"]