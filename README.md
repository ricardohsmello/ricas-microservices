# My Hello World from microservices

This is an example of microservices using Java. 

This repository has a distributed architecture system using four projects, where exists a service layer that invoke others two microservices, such spring boot and microprofile service. These microservices call backend api as you can see in image below:

![Quick Start architecture for ricardohsmello/microservices](https://imagizer.imageshack.com/v2/752x452q90/r/923/4wtnFL.png)

## This microservice project includes four projects
- ricas-microprofile
- ricas-backend
- ricas-microservices
- ricas-api-gateway

## Technology
- Spring boot
- Wildfly
- Apache Camel

# Usage
## Running
Navigate until ricas-backend root and run:
- mvn clean wildfly:run

Navigate until ricas-api-gateway and run:
- mvn spring-boot:run -Dserver.port=8380
  
Navigate until ricas-microservices and run:  
- mvn clean spring-boot:run -Dserver.port=8180

Navigate until ricas-microprofile and run: 
mvn thorntail:run -Dswarm.network.socket-binding-groups.standard-sockets.port-offset=200
 #### Note: the above command changes the default port of wildfly to not collide with backend wildfly 9090 port service 


## Testing
Type the follow URL on browser
http://localhost:8380/api/gateway

## Output
["Hello Spring Boot application from the cluster backend at host: 192.168.68.2","Hello from the cluster backend at host: 192.168.68.2"]
