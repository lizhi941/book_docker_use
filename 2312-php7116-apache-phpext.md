和制作php7.1.15-apache-phpext一样，只是php的版本换成7.1.16版本

```bash
FROM php:7.1.16-apache
RUN apt-get update && apt-get install -y \
libfreetype6-dev \
libjpeg62-turbo-dev \
libmcrypt-dev \
libpng-dev \
libxslt-dev \
libicu-dev \
&& docker-php-ext-install -j$(nproc) iconv mcrypt xsl intl pdo_mysql soap zip \
&& docker-php-ext-configure gd --with-freetype-dir=/usr/include/ --with-jpeg-dir=/usr/include/ \
&& docker-php-ext-install -j$(nproc) gd
```



