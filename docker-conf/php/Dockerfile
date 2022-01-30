FROM php:7.4-apache

ARG DOCKER_PHP_USER
ARG DOCKER_PHP_USER_UID

# stiahnutie potrebnych nastrojov do Linuxu (Debian-u)
# sposob zapisu RUN setri pocet vrstiev (velkost image-u) ale pri malej zmene sa prebuilduje cely RUN
RUN apt-get update && apt-get install -y \
		curl \
	    git \
	    libzip-dev \
	    unzip

RUN docker-php-ext-install -j$(nproc) \
        zip pdo pdo_mysql \
        && docker-php-ext-enable \
        pdo_mysql \
        && adduser --uid ${DOCKER_PHP_USER_UID} --disabled-password --disabled-login ${DOCKER_PHP_USER}

# stiahnutie a instalacia composer-u 2
# po nastartovani to budem potrebovat pre stiahnutie Nette sandbox prikladu
RUN curl -s https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer --2

USER php-user

# expose portu weboveho servera Apache (nepovinne, je to zahrnute v image, z ktoreho sa vychadza)
EXPOSE 80
