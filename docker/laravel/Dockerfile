FROM php:8.1.0-fpm

# TODO: php.iniを作成してコピーする

# Vite用
EXPOSE 5173 

# Node.jsのインストール
COPY --from=node:18.14.2 /usr/local/bin /usr/local/bin
COPY --from=node:18.14.2 /usr/local/lib /usr/local/lib

# パッケージインストール
RUN apt-get update
RUN apt-get -y install git zip unzip vim
RUN docker-php-ext-install pdo_mysql

# composerのインストール
RUN cd /usr/bin && curl -s http://getcomposer.org/installer | php && ln -s /usr/bin/composer.phar /usr/bin/composer

WORKDIR /var/www/html