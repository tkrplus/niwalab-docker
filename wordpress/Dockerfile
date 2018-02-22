FROM wordpress:latest
MAINTAINER tkrplus

RUN apt-get update
RUN apt-get -y install wget unzip

WORKDIR /tmp/wp-cli
RUN curl -O https://raw.githubusercontent.com/wp-cli/builds/gh-pages/phar/wp-cli.phar
RUN chmod +x wp-cli.phar
RUN mv wp-cli.phar /usr/local/bin/wp

WORKDIR /tmp/wp-plugins

RUN wget https://downloads.wordpress.org/plugin/rest-api.2.0-beta15.zip

RUN unzip './*.zip' -d /usr/src/wordpress/wp-content/plugins

RUN apt-get clean
RUN rm -rf /tmp/*

RUN chown -R www-data:www-data /usr/src/wordpress/wp-content

WORKDIR /var/www/html
