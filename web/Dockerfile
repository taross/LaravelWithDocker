FROM nginx:latest

RUN useradd -m -s /bin/bash -u 1000 taross && \
#nginx.conf
sed -i 's/user\ \ nginx\;/user\ \ taross\;/g' /etc/nginx/nginx.conf

ADD ./vhost.conf /etc/nginx/conf.d/default.conf
WORKDIR /var/www
