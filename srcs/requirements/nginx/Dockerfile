FROM debian:buster

RUN 	apt-get update -y
RUN	apt-get upgrade -y
RUN	apt-get install -y nginx
RUN	apt install vim -y
RUN	apt install curl -y
RUN	mkdir -p /etc/nginx/ssl
RUN	apt install openssl -y
RUN	openssl req -x509 -nodes -out /etc/nginx/ssl/inception.crt -keyout /etc/nginx/ssl/inception.key -subj "/C=FR/ST=IDF/L=Paris/O=42/OU=42/CN=ychibani.42.fr/UID=ychibani"
RUN	mkdir -p /var/run/nginx
RUN	chmod 755 /var/www/html
RUN	chown -R www-data:www-data /var/www/html
	
COPY ./conf/nginx.conf /etc/nginx/nginx.conf

EXPOSE 443

CMD [ "nginx", "-g", "daemon off;" ]
