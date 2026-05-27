FROM maven:3.9-eclipse-temurin-17 AS build
WORKDIR /app
COPY . .
RUN mvn clean package

FROM eclipse-temurin:17-jdk
WORKDIR /app
COPY --from=build /app/target/app-1.0.jar app.jar

EXPOSE 8080
CMD ["java","-jar","app.jar"]
