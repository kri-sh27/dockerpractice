# FROM maven:3.6.1-jdk-8-slim AS build
# RUN mkdir -p /workspace
# WORKDIR /workspace
# COPY pom.xml /workspace
# COPY src /workspace/src
# RUN mvn -f pom.xml clean package

# FROM openjdk:8-alpine
# COPY --from=build /workspace/target/*.jar app.jar
# EXPOSE 8099
# ENTRYPOINT ["java","-jar","app.jar"]

FROM openjdk:11

COPY target/HPI-0.0.1-SNAPSHOT.jar HPI-0.0.1-SNAPSHOT.jar
ENTRYPOINT ["java", "-jar", "HPI-0.0.1-SNAPSHOT.jar"]

EXPOSE 8099



# FROM openjdk:11-jre-slim
# WORKDIR /app
# COPY . .
# RUN ./mvnw clean package
# EXPOSE 8099
# ENTRYPOINT ["java", "-jar", "target/app.jar"]