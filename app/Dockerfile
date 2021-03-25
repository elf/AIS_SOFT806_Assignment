FROM ubuntu:20.04

RUN DEBIAN_FRONTEND=noninteractive apt-get update && \
    DEBIAN_FRONTEND=noninteractiv apt-get install -y locales && \
    rm -rf /var/lib/apt/lists/* && \
    localedef -i en_US -c -f UTF-8 -A /usr/share/locale/locale.alias en_US.UTF-8
ENV LANG en_US.utf8

RUN DEBIAN_FRONTEND=noninteractive apt-get update && \
    DEBIAN_FRONTEND=noninteractive apt-get install -yq --no-install-recommends \
      ca-certificates \
      curl \
      git \
      wget \
      ;

RUN curl -sL https://deb.nodesource.com/setup_12.x | DEBIAN_FRONTEND=noninteractive bash - && \
    DEBIAN_FRONTEND=noninteractive apt-get install -yq \
      build-essential \
      nodejs

RUN DEBIAN_FRONTEND=noninteractive apt-get install -yq --no-install-recommends \
      php7.4-cli \
      php7.4-json \
      php7.4-curl \
      php7.4-fpm \
      php7.4-gd \
      php7.4-mbstring \
      php7.4-pdo\
      php7.4-mysql \
      php7.4-xml \
      php7.4-zip \
      php7.4-intl \
      php7.4-xdebug \
      ;

      #php7.2-soap \
      #php7.2-sqlite3 \
      #php7.2-ldap \

RUN DEBIAN_FRONTEND=noninteractive apt-get install -yq --no-install-recommends \
      mariadb-server \
      ;

#RUN apt-get clean && rm -rf /var/lib/apt/lists/*

RUN DEBIAN_FRONTEND=noninteractive apt-get install -yq --no-install-recommends \
      curl \
      ;
RUN wget https://getcomposer.org/installer -O - | php -- --install-dir=/usr/local/bin/ --filename=composer
RUN wget https://get.symfony.com/cli/installer -O - | bash && mv $HOME/.symfony/bin/symfony /usr/local/bin/.

RUN mkdir -p /docroot
WORKDIR /docroot
CMD php -S 0.0.0.0:80 -t /docroot
