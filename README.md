# compose-java

#Dokerfile java
FROM openjdk
COPY src JavaDocker
WORKDIR JavaDocker
RUN mkdir -p bin
RUN javac -d bin ./com/myapp/Helloworld.java
WORKDIR bin
CMD ["java","com.myapp.Helloworld"]
