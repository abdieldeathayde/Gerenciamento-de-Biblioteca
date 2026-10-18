
# Etapa 1: compilar a aplicação com Maven e Java 21
FROM maven:3.9-eclipse-temurin-21 AS build

WORKDIR /app

COPY pom.xml ./

RUN mvn -B dependency:go-offline

COPY src/ src/

RUN mvn -B clean package -DskipTests \
    && cp target/*.jar app.jar

# Etapa 2: executar a aplicação
FROM eclipse-temurin:21-jre

WORKDIR /app

COPY --from=build /app/app.jar app.jar

EXPOSE 8083

ENTRYPOINT ["java", "-jar", "app.jar"]
