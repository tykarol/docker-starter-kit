FROM debian:jessie

ENV DEBIAN_FRONTEND noninteractive

# Install base packages
RUN apt-get update && apt-get install -y \
    nano \
    wget \
    curl \
    git

# Install apache2 & php5 packages
RUN apt-get install -y \
    apache2 apache2-doc apache2-utils \
    php5 libapache2-mod-php5 \
    php5-curl php5-json php5-mcrypt php5-readline php5-intl php5-tidy php5-mysql

RUN rm -rf /etc/apache2/sites-enabled/* /etc/apache2/sites-available/*
COPY cert/* /etc/apache2/ssl/
COPY vhost.conf /etc/apache2/sites-enabled/
COPY vhost.conf /etc/apache2/sites-available/
COPY php.ini /etc/php5/apache2/conf.d/99-overrides.ini
COPY php-cli.ini /etc/php5/cli/conf.d/99-overrides.ini

RUN a2enmod rewrite ssl

RUN usermod -u 1000 www-data

# Install nodejs
RUN curl -sL https://deb.nodesource.com/setup_9.x | bash - \
    && apt-get install -y nodejs build-essential

# RUN npm install -g webpack

# Install supervisor
RUN apt-get install -y supervisor
RUN mkdir -p /var/log/supervisor
COPY supervisor.conf /etc/supervisor/conf.d/
CMD supervisord -c /etc/supervisor/conf.d/supervisor.conf

# Clean
RUN apt-get clean && rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/* /usr/share/doc/*
