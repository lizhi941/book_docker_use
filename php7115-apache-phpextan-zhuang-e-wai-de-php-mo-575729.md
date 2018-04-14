#### 2.3.1.1 php7.1.15-apache-phpext

以官方镜像php：7.1.15-apache为基础，增加一些安装magento2需要的模块，如iconv mcrypt xsl intl pdo\_mysql soap zip，gd。这个Dockerfile也是根据php的官方docker仓库的例子写的。有示例说明如何安装php源码包中已有的模块和第三方模块。

```bash
FROM php:7.1.15-apache
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



