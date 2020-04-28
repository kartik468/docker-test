# Docker setup for sample spring boot app with tomcat, prometheus and grafana

## Setup tomcat image docker file with sample app
- first create tomcat image with

     $ sudo docker image build -t sample-spring-app .

- create wars folder in tomcat folder and add your wars in that

- create tomcat image with the Dockerfile present in tomcat folder

    $ sudo docker image build -t sample-spring-app .

## Run docker compose

- finally run docker compose file which is present in root folder
    
  $ sudo docker-compose up
  
