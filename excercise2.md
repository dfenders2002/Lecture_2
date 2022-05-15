# EXCERCISE 2 - Creating images and linking containers  

## Run my SQL
docker pull mysql:5.6
docker run --env MYSQL_ROOT_PASSWORD=quintor_pw --env MYSQL_DATABASE=cddb_quintor --env MYSQL_USER=cddb_quintor --env MYSQL_PASSWORD=quintor_pw -p 23306:3306 --name cddb_mysql  -d mysql:5.6

## Create a docker image of the java rest service
docker pull tomcat
docker build .
docker build -t dock1 .

## Run the java rest service
