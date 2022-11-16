#FROM maven:3.6.3-openjdk-17 as build
#COPY src /home/app/src
#COPY pom.xml /home/app
#RUN mvn -f /home/app/pom.xml clean package -Dmaven.test.skip=true
#
#FROM openjdk:17
#COPY --from=build /home/app/target/app.war /user/local/lib/app.war
##COPY target/app.war /user/local/lib/app.war
#EXPOSE 8082
#ENTRYPOINT ["java", "-jar", "/user/local/lib/app.war"]

FROM maven:3.6.3-openjdk-17 as build

ARG JAR_FILE=/target/*.war
COPY ${JAR_FILE} app.war
EXPOSE 8082
ENTRYPOINT ["java","-jar","/app.war"]