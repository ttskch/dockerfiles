FROM nginx

ENV NGINX_CONFD_DIR /etc/nginx/conf.d

COPY default.conf $NGINX_CONFD_DIR/

WORKDIR $NGINX_CONFD_DIR
ENV DOCROOT /docroot

CMD sed -i "s|%%DOCROOT%%|$DOCROOT|g" default.conf && nginx -g 'daemon off;'
