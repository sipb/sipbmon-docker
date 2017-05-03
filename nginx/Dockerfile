FROM library/nginx:stable
RUN rm /etc/nginx/conf.d/default.conf
COPY *.conf /etc/nginx/conf.d/
EXPOSE 80 443
