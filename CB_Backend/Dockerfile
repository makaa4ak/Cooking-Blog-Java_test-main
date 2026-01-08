# Этап 1 — сборка на JDK 17 (поддерживаемый)
FROM eclipse-temurin:17-jdk AS builder
WORKDIR /app

# Копируем Gradle
COPY gradlew .
COPY gradle gradle
COPY build.gradle settings.gradle ./

# Копируем исходники
COPY src src

RUN chmod +x gradlew
RUN ./gradlew build -x test --no-daemon

# Этап 2 — финальный образ (JRE 17)
FROM eclipse-temurin:17-jre AS runtime
WORKDIR /app

COPY --from=builder /app/build/libs/*.jar app.jar

ENV PORT=8080
EXPOSE ${PORT}

ENTRYPOINT ["sh", "-c", "java -Dserver.port=${PORT} -jar app.jar"]
