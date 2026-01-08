# 1. Базовый образ Maven + JDK 17 (официальный, доступен)
FROM maven:3.9.8-openjdk-17

# 2. Копируем весь проект
COPY . /app
WORKDIR /app

# 3. Собираем проект (без тестов)
RUN mvn clean package -DskipTests

# 4. Открываем порт 8080
EXPOSE 8080

# 5. Старт приложения
CMD ["java", "-jar", "target/CB_Backend-0.0.1-SNAPSHOT.jar"]
