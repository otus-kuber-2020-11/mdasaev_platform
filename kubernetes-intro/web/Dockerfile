FROM ubuntu:latest


WORKDIR /app

RUN apt-get update
RUN apt-get install -y nginx
COPY ./default /etc/nginx/sites-available/
COPY ./README.md ./

RUN chmod a+x /usr/sbin/nginx && chmod 777 /var/log/nginx/* && chmod 777 /var/lib/nginx
RUN touch /run/nginx.pid && chmod 777 /run/nginx.pid


RUN useradd -m -u 1001 charlie
USER charlie

CMD ["/usr/sbin/nginx", "-g", "daemon off;"]
