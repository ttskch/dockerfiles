FROM composer

ARG version

RUN composer global require deployer/deployer:$version
ENV PATH $PATH:/tmp/vendor/bin
