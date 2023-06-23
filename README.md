### Cofig-Server
1. Here we created one microservice 'configServer'.
2. To make this service as config-server we need to add two dependencies -
    1. One is for 'Config-Server'
    ```groovy
   	implementation 'org.springframework.cloud:spring-cloud-config-server'
   ```
   2. Second is for Eureka-client 
    ```groovy
    implementation 'org.springframework.cloud:spring-cloud-starter-netflix-eureka-client'
   ```
3. After including all the dependencies we need to define one annotation in the main class ***@EnableConfigServer***.
4. We need to add below dependencies to connect with github repo where our Configurations are present -
```yaml
spring:
  application:
    name: Config-Server
  cloud:
    config:
      server:
        git:
          uri: https://github.com/ayushdgupta/SpringBoot3-ConfigFiles-ConfigServer-Microservice
          clone-on-start: true
```
5. Above props are the properties that we need to add in most of the cases, apart from that we might need to add other configuration according to our need.
6. URL to see default application.yml file from github is - http://guptaji:9094/application/default
7. Now our microservice is ready as a config server now any microservice using config-client can fetch the properties from it.
8. Microservices using this config-server are as follows -
    1. [Hotel microservice](https://github.com/ayushdgupta/SpringBoot3-Hotel-Microservice).
    2. [User microservice](https://github.com/ayushdgupta/SpringBoot3-User-Microservice/tree/master).
    3. [Rating microservice](https://github.com/ayushdgupta/SpringBoot3-Rating-Microservice).
    4. [API Gateway](https://github.com/ayushdgupta/SpringBoot3-APIGateway-Microservice)
9. Below is the Eureka Server where this Config-Server is configured -  
    [Eureka Server](https://github.com/ayushdgupta/SpringBoot3-Eureka-Service-Microservice)
10. Github link of config-files -
    [Config-Files](https://github.com/ayushdgupta/SpringBoot3-ConfigFiles-ConfigServer-Microservice)


### Imporatnt links  
1. https://cloud.spring.io/spring-cloud-config/multi/multi__spring_cloud_config_server.html