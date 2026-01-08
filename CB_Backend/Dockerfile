# Рабочий образ Maven + JDK 17
FROM maven:3.8.8-openjdk-17

# Копируем проект
COPY . /app
WORKDIR /app

# Собираем проект без тестов
RUN mvn clean package -DskipTests

# Открываем порт 8080
EXPOSE 8080

# Старт приложения
CMD ["java", "-jar", "target/CB_Backend-0.0.1-SNAPSHOT.jar"]
