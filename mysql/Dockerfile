# build with 
# docker build -t [image_name] .
#
# run with
# docker run -d --name [container_name] --env-file ./conf/environment.conf [image_name]

FROM mysql

ENV MYSQL_DATABASE company

# Add sql-scripts to run at startup (docker-entrypoint-initdb.d/)
COPY ./mysql-scripts/ /docker-entrypoint-initdb.d/
