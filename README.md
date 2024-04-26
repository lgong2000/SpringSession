# SpringSession

Spring Web - Web
Spring Security - Security
Spring Session - Web
Spring Data Redis (Access+Driver) - NoSQL

Version 1
Disable redis in pom.xml
Run - Console:
Using generated security password: 1270caad-15c6-4861-b0aa-2a85e7b7f9bf
Username: user
Chrome - http://localhost:8080/
Inspect - Application - Storage - Cookies - JSESSIONID
Every time the Application Server Restart - Session Changed

Version 2
#error spring Cannot connect to the Docker daemon at npipe:////./pipe/dock
  -> Docker Service(Docker Desktop) is needed

Docker Compose need Spring Boot 3.1+
pom.xml
    <dependency>
        <groupId>org.springframework.boot</groupId>
        <artifactId>spring-boot-docker-compose</artifactId>
    </dependency>

docker-compose.yml
    version: '3.2'
    services:
    redis:
    image: "redis:alpine"
    ports:
    - "6379:6379"

application.properties
    spring.docker.compose.lifecycle-management=start_only

Docker Command:
Terminal Window:
docker ps ##list docker image run status
docker exec -it springsession-redis-1 redis-cli ##run a client
    127.0.0.1:6379> keys *  ##list key
