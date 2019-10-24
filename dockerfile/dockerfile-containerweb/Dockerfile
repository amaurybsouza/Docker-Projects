FROM debian:9
RUN apt-get update && apt-get install apache2 -y
WORKDIR /var/www/html
COPY index.html .
EXPOSE 80
CMD ["/usr/sbin/apache2ctl", "-D", "FOREGROUND"]
