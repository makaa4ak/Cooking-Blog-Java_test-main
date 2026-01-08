# 1. Базовый образ OpenJDK 17 (доступен точно)
FROM openjdk:17-slim

# 2. Копируем весь проект
COPY . /app
WORKDIR /app

# 3. Устанавливаем Maven вручную
RUN apt-get update && apt-get install -y maven

# 4. Собираем проект без тестов
RUN mvn clean package -DskipTests

# 5. Открываем порт 8080
EXPOSE 8080

# 6. Старт приложения
CMD ["java", "-jar", "target/CB_Backend-0.0.1-SNAPSHOT.jar"]
