FROM php:7.1.10-fpm
MAINTAINER wubaiqing <wubaiqing@vip.qq.com>

# 阿里源
ADD sources.list /etc/apt/sources.list

RUN apt-get update && apt-get install -y \
  wget \
  curl \
  git \
  libmemcached-dev 
  libmcrypt-dev \
  zlib1g-dev \
  libxml2-dev \
  autoconf \
  libfreetype6-dev \
  libjpeg62-turbo-dev \
  libpng-dev \
  && docker-php-ext-install mcrypt mysqli mbstring pdo pdo_mysql

RUN pecl install redis-3.1.0 \
  && pecl install xdebug-2.5.0 \
  && pecl install memcached-2.2.0 \
  && docker-php-ext-enable redis xdebug memcached

