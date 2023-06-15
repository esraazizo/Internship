# This program is very simple, it connects to a MySQL database based on the following env vars:

 * MYSQL_HOST
 * MYSQL_USER
 * MYSQL_PASS
 * MYSQL_PORT
 
Requirements :

 - Dockerfile that build the application.
 - Pipeline job (jenkinsfile) to build the application using dockerfile and reports if any errors happened in the build.
 - The output of the build step should be a docker image pushed to dockerhub. 
 - Docker compose file that contains both application and mysql database to the application locally.
 - Helm manifests for kubernetes to deploy the application using them on kubernetes with adding config to support high availability and volume persistence and exposing service to the public.
 
 
1- Create Dockerfile to dockerize the app. 
2- Build the app.
          
     docker build . -t esraazizo/esraa-go-app
      
   <img src="ScreenShots/2.png" width=600 >
   
3- Create docker compose file that contain 2 services for mysql and the application.
 
   <img src="ScreenShots/3.png" width=600 >
   
   <img src="ScreenShots/4.png" width=600 >

4- Check the application locally.
 
   - on port 9090 return null.
   
   <img src="ScreenShots/5.png" width=600 >
   
   - On /healthcheck it returns an OK message.
   
   <img src="ScreenShots/6.png" width=600 >
  
   - On GET it return null.
  
   <img src="ScreenShots/7.png" width=600 >
  
   - On POST it creates a new row.
  
   <img src="ScreenShots/8.png" width=600 >
 
   - On GET it return 1 row and so on.
  
   <img src="ScreenShots/9.png" width=600 >
   
   - Check On port 9090 it create 2 rows.
   
   <img src="ScreenShots/10.png" width=600 >
   
5- Installing jenkins using Docker on port 8080.

   <img src="ScreenShots/11.png" width=600 >
   
   - Login Jenkins and get password of admin.
   
   <img src="ScreenShots/12.png" width=600 >
   
   <img src="ScreenShots/13.png" width=600 >
   
   - Getting started Jenkins.
  
   <img src="ScreenShots/14.png" width=600 >
   
   - Create new Credential of Docker-Hub.
   
   <img src="ScreenShots/15.png" width=600 >
   
   <img src="ScreenShots/16.png" width=600 >

   - Create new Pipeline.

   <img src="ScreenShots/17.png" width=600 >
   
   <img src="ScreenShots/18.png" width=600 >

6- Build Pipeline.
  
   <img src="ScreenShots/25.png" width=600 >
   
7- Docker Image was pushed to dockerhub successfully.

   <img src="ScreenShots/24.png" width=600 >
 
8- After installing helm tool on minikube or working with cluster do the next command 

    helm install go-app ./esraa-go-app 

9- Finally run the application locally.

   <img src="ScreenShots/24.png" width=600 >

 



