FROM maven:3.6.3-openjdk-17 as build
COPY src /home/app/src
COPY pom.xml /home/app
RUN mvn -f /home/app/pom.xml clean package -Dmaven.test.skip=true

FROM openjdk:17
COPY --from=build /home/app/target/app.jar /user/local/lib/app.jar
#COPY target/app.jar /user/local/lib/app.jar
EXPOSE 8080
ENTRYPOINT ["java", "-jar", "/user/local/lib/app.jar"]

#FROM maven:3.6.3-openjdk-17 as build
#
#ARG JAR_FILE=/target/*.jar
#COPY ${JAR_FILE} app.jar
#RUN mvn -f /home/app/pom.xml clean package -Dmaven.test.skip=true
#EXPOSE 8080
#ENTRYPOINT ["java","-jar","/app.jar"]