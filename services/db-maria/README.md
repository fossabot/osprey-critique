Pure configuration for the docker image for the Mariadb

docker run --name osprey-maria -p 3306:3306 -e MYSQL_ROOT_PASSWORD=mypass -d mariadb
docker run -it --link osprey-maria:mysql --rm mariadb sh -c 'exec mysql -h"$MYSQL_PORT_3306_TCP_ADDR" -P"$MYSQL_PORT_3306_TCP_PORT" -uroot -p"$MYSQL_ENV_MYSQL_ROOT_PASSWORD"'

mysqldump -uroot osprey