ARG MYSQL_VERSION=8.0
FROM mysql/mysql-server:${MYSQL_VERSION}

# ARG TZ=PRC
# ENV TZ ${TZ}
# RUN ln -snf /usr/share/zoneinfo/$TZ /etc/localtime && echo $TZ > /etc/timezone 

COPY my.cnf /etc/mysql/conf.d/my.cnf

CMD ["mysqld"]

EXPOSE 3306