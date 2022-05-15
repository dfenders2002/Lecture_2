# -Daan Enders 1018410
# Lecture_2
## EXCERCISE 1 WORKING WITH CONTAINERS  
### THE BASIC COMMANDS TO START WITH  
docker help   
docker help build   
docker images   
docker ps      
docker ps -a    

### Starting a container  
docker run --name Lecture2Container -d -p 20080:80 nginx:alpine  
http://localhost:20080/  

### Looking inside a container   
Lecture2Container   
ls   
ps -ef  
hostname  
hostname -i  
exit  

### Stopping and restarting a container  
docker stop Lecture2Container  
docker ps -a

### Removing containers and images  
docker rm Lecture2Container  
docker rmi nginx:alpine  
Untagged: nginx:alpine  
Untagged: nginx@sha256:5a0df7fb7c8c03e4158ae9974bfbd6a15da2bdfdeded4fb694367ec812325d31  
Deleted: sha256:51696c87e77e4ff7a53af9be837f35d4eacdb47b4ca83ba5fd5e4b5101d98502  

### Volume mounting  
docker run --name VolumeMounting -d -p 20080:80 -v C:\CloudDevGit\Lecture_2\www:/usr/share/nginx/html:ro nginx:alpine