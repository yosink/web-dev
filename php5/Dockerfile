FROM php:5.6-fpm

RUN mv /etc/apt/sources.list /etc/apt/sources.list.backup \
	&& echo "deb http://mirrors.aliyun.com/debian stretch main contrib non-free" >> /etc/apt/sources.list && \		
	echo "deb http://mirrors.aliyun.com/debian stretch-proposed-updates main contrib non-free" >> /etc/apt/sources.list && \
	echo "deb http://mirrors.aliyun.com/debian stretch-updates main contrib non-free" >> /etc/apt/sources.list && \
	echo "deb-src http://mirrors.aliyun.com/debian stretch main contrib non-free" >> /etc/apt/sources.list && \
	echo "deb-src http://mirrors.aliyun.com/debian stretch-proposed-updates main contrib non-free" >> /etc/apt/sources.list && \
	echo "deb-src http://mirrors.aliyun.com/debian stretch-updates main contrib non-free" >> /etc/apt/sources.list && \
	echo "deb http://mirrors.aliyun.com/debian-security/ stretch/updates main non-free contrib" >> /etc/apt/sources.list && \
	echo "deb-src http://mirrors.aliyun.com/debian-security/ stretch/updates main non-free contrib" >> /etc/apt/sources.list && \
	echo "deb http://mirrors.aliyuncs.com/debian stretch main contrib non-free" >> /etc/apt/sources.list && \
	echo "deb http://mirrors.aliyuncs.com/debian stretch-proposed-updates main contrib non-free" >> /etc/apt/sources.list && \
	echo "deb http://mirrors.aliyuncs.com/debian stretch-updates main contrib non-free" >> /etc/apt/sources.list && \
	echo "deb-src http://mirrors.aliyuncs.com/debian stretch main contrib non-free" >> /etc/apt/sources.list && \
	echo "deb-src http://mirrors.aliyuncs.com/debian stretch-proposed-updates main contrib non-free" >> /etc/apt/sources.list && \
	echo "deb-src http://mirrors.aliyuncs.com/debian stretch-updates main contrib non-free" >> /etc/apt/sources.list && \
	echo "deb http://mirrors.aliyuncs.com/debian-security/ stretch/updates main non-free contrib" >> /etc/apt/sources.list && \
	echo "deb-src http://mirrors.aliyuncs.com/debian-security/ stretch/updates main non-free contrib" >> /etc/apt/sources.list && \
	apt-get update && apt-get install -y \
	libfreetype6-dev \
	libjpeg62-turbo-dev \
	libpng-dev \
	libzip-dev \
	procps \
	&& docker-php-ext-install -j$(nproc) iconv \
	&& docker-php-ext-configure gd --with-freetype-dir=/usr/include/ --with-jpeg-dir=/usr/include/ \
	&& docker-php-ext-install -j$(nproc) gd \ 
	&& docker-php-ext-configure zip --with-libzip \
	&& docker-php-ext-install zip \
	&& docker-php-ext-install bcmath \
	&& docker-php-ext-install mysql pdo pdo_mysql


COPY ./redis-4.2.0.tgz /tmp
RUN mkdir -p /tmp/redis \
	&& tar -xf /tmp/redis-4.2.0.tgz -C /tmp/redis --strip-components=1 \
	&& rm /tmp/redis-4.2.0.tgz \
	&& docker-php-ext-configure /tmp/redis \
	&& docker-php-ext-install /tmp/redis \
	&& rm -r /tmp/redis

RUN apt-get clean && \
	rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/* && \
	rm /var/log/lastlog /var/log/faillog

COPY ./php5.6.ini /usr/local/etc/php/php.ini

USER root

RUN usermod -u 1000 www-data

WORKDIR /var/www

CMD ["php-fpm"]

EXPOSE 9000

FROM php:5.6-fpm

RUN mv /etc/apt/sources.list /etc/apt/sources.list.backup \
	&& echo "deb http://mirrors.aliyun.com/debian stretch main contrib non-free" >> /etc/apt/sources.list && \		
	echo "deb http://mirrors.aliyun.com/debian stretch-proposed-updates main contrib non-free" >> /etc/apt/sources.list && \
	echo "deb http://mirrors.aliyun.com/debian stretch-updates main contrib non-free" >> /etc/apt/sources.list && \
	echo "deb-src http://mirrors.aliyun.com/debian stretch main contrib non-free" >> /etc/apt/sources.list && \
	echo "deb-src http://mirrors.aliyun.com/debian stretch-proposed-updates main contrib non-free" >> /etc/apt/sources.list && \
	echo "deb-src http://mirrors.aliyun.com/debian stretch-updates main contrib non-free" >> /etc/apt/sources.list && \
	echo "deb http://mirrors.aliyun.com/debian-security/ stretch/updates main non-free contrib" >> /etc/apt/sources.list && \
	echo "deb-src http://mirrors.aliyun.com/debian-security/ stretch/updates main non-free contrib" >> /etc/apt/sources.list && \
	echo "deb http://mirrors.aliyuncs.com/debian stretch main contrib non-free" >> /etc/apt/sources.list && \
	echo "deb http://mirrors.aliyuncs.com/debian stretch-proposed-updates main contrib non-free" >> /etc/apt/sources.list && \
	echo "deb http://mirrors.aliyuncs.com/debian stretch-updates main contrib non-free" >> /etc/apt/sources.list && \
	echo "deb-src http://mirrors.aliyuncs.com/debian stretch main contrib non-free" >> /etc/apt/sources.list && \
	echo "deb-src http://mirrors.aliyuncs.com/debian stretch-proposed-updates main contrib non-free" >> /etc/apt/sources.list && \
	echo "deb-src http://mirrors.aliyuncs.com/debian stretch-updates main contrib non-free" >> /etc/apt/sources.list && \
	echo "deb http://mirrors.aliyuncs.com/debian-security/ stretch/updates main non-free contrib" >> /etc/apt/sources.list && \
	echo "deb-src http://mirrors.aliyuncs.com/debian-security/ stretch/updates main non-free contrib" >> /etc/apt/sources.list && \
	apt-get update && apt-get install -y \
	libfreetype6-dev \
	libjpeg62-turbo-dev \
	libpng-dev \
	libzip-dev \
	procps \
	&& docker-php-ext-install -j$(nproc) iconv \
	&& docker-php-ext-configure gd --with-freetype-dir=/usr/include/ --with-jpeg-dir=/usr/include/ \
	&& docker-php-ext-install -j$(nproc) gd \ 
	&& docker-php-ext-configure zip --with-libzip \
	&& docker-php-ext-install zip \
	&& docker-php-ext-install bcmath \
	&& docker-php-ext-install mysql pdo pdo_mysql


COPY ./redis-4.2.0.tgz /tmp
RUN mkdir -p /tmp/redis \
	&& tar -xf /tmp/redis-4.2.0.tgz -C /tmp/redis --strip-components=1 \
	&& rm /tmp/redis-4.2.0.tgz \
	&& docker-php-ext-configure /tmp/redis \
	&& docker-php-ext-install /tmp/redis \
	&& rm -r /tmp/redis

RUN apt-get clean && \
	rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/* && \
	rm /var/log/lastlog /var/log/faillog

COPY ./php5.6.ini /usr/local/etc/php/php.ini

USER root

RUN usermod -u 1000 www-data

WORKDIR /var/www

CMD ["php-fpm"]

EXPOSE 9000
