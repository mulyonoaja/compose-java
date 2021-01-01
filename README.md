# compose-java

#Dokerfile java
FROM openjdk
COPY src JavaDocker
WORKDIR JavaDocker
RUN mkdir -p bin
RUN javac -d bin ./com/myapp/Helloworld.java
WORKDIR bin
CMD ["java","com.myapp.Helloworld"]

#Springboot
FROM openjdk:latest
ADD target/springboot:docker-0.0.1-SNAPSHOT.jar app.jar
ENTRYPOINT ["java", ".jar","app.jar"]
EXPOSE 8080

