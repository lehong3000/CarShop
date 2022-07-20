FROM  alpine:latest as build
WORKDIR /
COPY ./auto_quickstart/auto_home1_quickstart_on_prestashop_1.7.2.2.zip .
RUN unzip -q auto_home1_quickstart_on_prestashop_1.7.2.2.zip

FROM prestashop/prestashop:1.7.8.6-apache
RUN rm -Rf /var/www/html && mkdir /var/www/html && chown www-data:www-data /var/www/html && chmod 777 /var/www/html
COPY --chown=www-data:www-data --chmod=755 --from=build /auto_store_home1_qs /var/www/html
EXPOSE 80