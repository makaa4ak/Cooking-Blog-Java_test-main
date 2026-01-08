# 1. Базовый образ с Maven + JDK 25
FROM maven:3.9.5-eclipse-temurin-25

# 2. Копируем весь проект
COPY . /app
WORKDIR /app

# 3. Собираем проект (без тестов)
RUN mvn clean package -DskipTests

# 4. Открываем порт 8080
EXPOSE 8080

# 5. Старт приложения
CMD ["java", "-jar", "target/CB_Backend-0.0.1-SNAPSHOT.jar"]
