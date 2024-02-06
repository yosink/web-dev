FROM php:7.2

RUN apt-get update && apt-get install -y \
	libfreetype6-dev \
	libjpeg62-turbo-dev \
	libpng-dev \
	libzip-dev \
	libpq-dev \
	procps \
	&& docker-php-ext-install -j$(nproc) iconv \
	&& docker-php-ext-configure gd --with-freetype-dir=/usr/include/ --with-jpeg-dir=/usr/include/ \
	&& docker-php-ext-install -j$(nproc) gd \ 
	&& docker-php-ext-configure zip --with-libzip \
	&& docker-php-ext-install zip \
	&& docker-php-ext-install bcmath \
	&& docker-php-ext-install mysqli pdo pdo_mysql pdo_pgsql

COPY ./swoole-4.2.7.tgz /tmp
RUN mkdir -p /tmp/swoole \
	&& tar -xf /tmp/swoole-4.2.7.tgz -C /tmp/swoole --strip-components=1 \
	&& rm /tmp/swoole-4.2.7.tgz \
	&& docker-php-ext-configure /tmp/swoole \
	&& docker-php-ext-install /tmp/swoole \
	&& rm -r /tmp/swoole

RUN apt-get clean && \
	rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/* && \
	rm /var/log/lastlog /var/log/faillog

COPY ./php7.2.ini /usr/local/etc/php/php.ini

WORKDIR /var/www

EXPOSE 9099
FROM php:7.2

RUN apt-get update && apt-get install -y \
	libfreetype6-dev \
	libjpeg62-turbo-dev \
	libpng-dev \
	libzip-dev \
	libpq-dev \
	procps \
	&& docker-php-ext-install -j$(nproc) iconv \
	&& docker-php-ext-configure gd --with-freetype-dir=/usr/include/ --with-jpeg-dir=/usr/include/ \
	&& docker-php-ext-install -j$(nproc) gd \ 
	&& docker-php-ext-configure zip --with-libzip \
	&& docker-php-ext-install zip \
	&& docker-php-ext-install bcmath \
	&& docker-php-ext-install mysqli pdo pdo_mysql pdo_pgsql

COPY ./swoole-4.2.7.tgz /tmp
RUN mkdir -p /tmp/swoole \
	&& tar -xf /tmp/swoole-4.2.7.tgz -C /tmp/swoole --strip-components=1 \
	&& rm /tmp/swoole-4.2.7.tgz \
	&& docker-php-ext-configure /tmp/swoole \
	&& docker-php-ext-install /tmp/swoole \
	&& rm -r /tmp/swoole

RUN apt-get clean && \
	rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/* && \
	rm /var/log/lastlog /var/log/faillog

COPY ./php7.2.ini /usr/local/etc/php/php.ini

WORKDIR /var/www

EXPOSE 9099