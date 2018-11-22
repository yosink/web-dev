FROM nginx:1.14

COPY nginx.conf /etc/nginx/

RUN apt-get update && apt-get install procps && rm /etc/nginx/conf.d/default.conf

RUN apt-get clean && \
    rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/* && \
    rm /var/log/lastlog /var/log/faillog

RUN usermod -u 1000  www-data

CMD ["nginx"]

EXPOSE 80 443