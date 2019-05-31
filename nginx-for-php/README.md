# nginx-for-php

## Precaution

When you use this image with other image which offers php-fpm (like [ttskch/php-fpm](https://cloud.docker.com/u/ttskch/repository/docker/ttskch/php-fpm)), you must mount php files onto the same path of this image (i.e. `/docroot`) to let the php-fpm container have the file corresponding passed [SCRIPT_FILENAME](default.conf#L10).

Following is an example of docker-compose.yml.

```yaml
version: '2'
services:
  php:
    image: ttskch/php-fpm
    volumes:         # these lines are required
      - .:/docroot   # to execute php scripts
  nginx:
    image: ttskch/nginx-for-php
    volumes:
      - .:/docroot
    ports:
      - "80:80"
```

Refs: https://wp.sjmf.in/?p=152
