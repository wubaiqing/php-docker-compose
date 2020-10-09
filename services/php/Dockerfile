FROM php:7.1.10-fpm
MAINTAINER wubaiqing <wubaiqing@vip.qq.com>

# 阿里源
# ADD sources.list /etc/apt/sources.list

# 安装依赖
RUN apt-get update && apt-get install -y \
  vim \
  wget \
  curl \
  git \
  libmemcached-dev \
  libmcrypt-dev \
  zlib1g-dev \
  libxml2-dev \
  autoconf \
  libfreetype6-dev \
  libjpeg62-turbo-dev \
  libpng-dev 

RUN docker-php-ext-install mcrypt mysqli mbstring pdo pdo_mysql
RUN pecl channel-update pecl.php.net && pecl install memcached redis && docker-php-ext-enable memcached redis
RUN usermod -u 1000 www-data

WORKDIR /var/www

CMD ["php-fpm"]

EXPOSE 9000

