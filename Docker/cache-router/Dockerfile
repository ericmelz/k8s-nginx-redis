FROM openresty/openresty
RUN apt update
RUN apt install -y emacs-nox
RUN apt install -y luarocks
RUN luarocks install md5

COPY content/conf/nginx.conf /usr/local/openresty/nginx/conf

CMD ["/usr/local/openresty/bin/openresty", "-g", "daemon off;"]