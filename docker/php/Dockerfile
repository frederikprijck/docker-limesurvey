FROM php:7.0-fpm
RUN apt-get update
RUN apt-get -y install git

RUN docker-php-ext-install pdo_mysql \
    && docker-php-ext-install json



RUN git clone https://github.com/LimeSurvey/LimeSurvey.git /limesurvey


RUN file="$(ls -1 /limesurvey)" && echo $file

RUN mv /limesurvey /var/www/html; \
	mkdir -p /uploadstruct; \
	chown -R www-data:www-data /var/www/html/limesurvey

RUN chmod -R 777 /var/www/html/limesurvey
RUN chown -R nobody:nogroup /var/www/html/limesurvey

RUN file="$(ls -1 /var/www/html)" && echo $file
RUN file="$(ls -1 /var/www/html/limesurvey)" && echo $file

VOLUME /var/www/html/limesurvey/upload



