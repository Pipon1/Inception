FROM debian:bullseye

COPY tools/ /var/www/

RUN sh /var/www/php-install.sh

RUN rm -rf /etc/php/8.2/fpm/pool.d/www.conf

COPY ./conf/ /etc/php/8.2/fpm/pool.d/

EXPOSE 9000

RUN chmod 777 /var/www/ -R

ENTRYPOINT [ "/var/www/wp-install.sh" ]

CMD ["php-fpm8.2","-F","-R"]