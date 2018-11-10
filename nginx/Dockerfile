FROM nginx:1.14

COPY nginx.conf /etc/nginx/

RUN rm /etc/nginx/conf.d/default.conf

RUN usermod -u 1000  www-data

CMD ["nginx"]

EXPOSE 80 443