FROM maven:3.9.6-eclipse-temurin-21-jammy AS build

WORKDIR /app

COPY pom.xml .

COPY . .

RUN mvn clean package

FROM eclipse-temurin:21-jre

WORKDIR /app

COPY --from=build /app/target/mobileid-1.0.jar .

EXPOSE 8080

CMD ["java", "-jar", "backend-1.0.jar"]