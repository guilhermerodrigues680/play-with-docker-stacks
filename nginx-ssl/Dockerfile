FROM nginx:1.19.3

RUN apt-get install openssl

COPY default.conf /etc/nginx/conf.d/default.conf

RUN openssl req -x509 -nodes -days 365 \
    -subj "/C=BR/ST=MG/O=Company, Inc./CN=mydomain.com" \
    -addext "subjectAltName=DNS:mydomain.com" -newkey rsa:2048 \
    -keyout /etc/ssl/private/nginx-selfsigned.key \
    -out /etc/ssl/certs/nginx-selfsigned.crt
