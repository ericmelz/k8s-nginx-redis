FROM openresty/openresty
RUN apt update
RUN apt install -y emacs-nox
RUN apt install -y luarocks

COPY content/conf/nginx.conf /usr/local/openresty/nginx/conf
COPY content/html /usr/local/openresty/nginx/html

CMD ["/usr/local/openresty/bin/openresty", "-g", "daemon off;"]