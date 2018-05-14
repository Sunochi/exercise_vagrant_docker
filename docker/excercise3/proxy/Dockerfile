FROM ubuntu
MAINTAINER sunochi

RUN apt-get update
RUN apt-get install -y nano wget dialog net-tools
RUN apt-get install -y nginx

RUN chown -R www-data:www-data /var/lib/nginx

RUN rm -v /etc/nginx/nginx.conf
ADD nginx-sites.conf /etc/nginx/nginx.conf

RUN echo "daemon off;" >> /etc/nginx/nginx.conf

EXPOSE 80
EXPOSE 443

COPY ./sslcerts/cert.pem /etc/ssl/mydomainA_cert.pem
COPY ./sslcerts/key.pem /etc/ssl/mydomainA_key.pem

CMD service nginx start
