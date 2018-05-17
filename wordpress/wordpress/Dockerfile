FROM wordpress:php7.1-fpm-alpine
MAINTAINER tkrplus

RUN apk add --update --no-cache wget unzip && \
    rm -rf /var/lib/apt/lists/*

WORKDIR /tmp/wp-cli
RUN curl -O https://raw.githubusercontent.com/wp-cli/builds/gh-pages/phar/wp-cli.phar && \
    chmod +x wp-cli.phar && \
    mv wp-cli.phar /usr/local/bin/wp

WORKDIR /tmp/wp-plugins

RUN wget https://downloads.wordpress.org/plugin/rest-api.2.0-beta15.zip && \
    unzip './*.zip' -d /usr/src/wordpress/wp-content/plugins && \
    rm rest-api.2.0-beta15.zip

RUN chown -R www-data:www-data /usr/src/wordpress/wp-content

WORKDIR /var/www/html
