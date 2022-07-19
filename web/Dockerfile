FROM  alpine:latest as build
WORKDIR /
COPY ./auto_home1_quickstart_on_prestashop_1.7.2.2.zip .
RUN unzip -q auto_home1_quickstart_on_prestashop_1.7.2.2.zip

FROM prestashop/prestashop:1.7.2.2
WORKDIR /
RUN rm -Rf /var/www/html && mkdir /var/www/html
COPY --from=build /auto_store_home1_qs /var/www/html
EXPOSE 80