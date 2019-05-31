FROM alpine

WORKDIR /docroot

RUN apk update \
    # install nginx and create default pid directory
    && apk add nginx \
    && mkdir -p /run/nginx \
    \
    # forward nginx logs to docker log collector
    && sed -i -E "s/error_log .+/error_log \/dev\/stderr warn;/" /etc/nginx/nginx.conf \
    && sed -i -E "s/access_log .+/access_log \/dev\/stdout main;/" /etc/nginx/nginx.conf \
    \
    # remove caches to decrease image size
    && rm -rf /var/cache/apk/*

ENV NGINX_CONFD_DIR /etc/nginx/conf.d

COPY default.conf $NGINX_CONFD_DIR/

EXPOSE 80

CMD ["nginx", "-g", "daemon off;"]
