# EXCERCISE 2 - Creating images and linking containers  

## Run my SQL
docker pull mysql:5.6
docker run --env MYSQL_ROOT_PASSWORD=quintor_pw --env MYSQL_DATABASE=cddb_quintor --env MYSQL_USER=cddb_quintor --env MYSQL_PASSWORD=quintor_pw -p 23306:3306 --name cddb_mysql  -d mysql:5.6 

## Create a docker image of the java rest service
docker pull tomcat
docker build . 
docker build -t cddb_backend . 
## Run the java rest service
docker run -d --link cddb_mysql:mysql --name cddb_backend -p 28080:8080 cddb_backend
## CREATE A DOCKER IMAGE OF THE ANGULAR WEB APP  
docker build -t cddb_frontend .  
docker tag 6796cb406524 cddb_frontend:latest    
## RUN THE ANGULAR WEB APP  
docker run -d --link cddb_backend:backend --name cddb_frontend -p 20080:80 cddb_frontend
## STORE THE DATABASE FILES ON THE HOST SYSTEM
docker run -v C:\CloudDevGit\Lecture_2\frontend\database:/var/lib/mysql --env MYSQL_ROOT_PASSWORD=quintor_pw --env MYSQL_DATABASE=cddb_quintor --env MYSQL_USER=cddb_quintor --env MYSQL_PASSWORD=quintor_pw -p 23306:3306 --name cddb_mysql -d mysql:5.6 

docker run -d --name cddb_mysql -p 23306:3306 -v C:\CloudDevGit\Lecture_2\frontend\database:/var/lib/mysql -e MYSQL_ROOT_PASSWORD=quintor_pw -e MYSQL_DATABASE=cddb_quintor -e MYSQL_USER=cddb_quintor -e MYSQL_PASSWORD=quintor_pw mysql:5.6