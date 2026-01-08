# Используем Java 25
FROM eclipse-temurin:25-jdk

# Копируем backend
COPY . /app
WORKDIR /app

# Собираем проект
RUN ./mvnw clean package -DskipTests

# Открываем порт 8080
EXPOSE 8080

# Запуск приложения
CMD ["java", "-jar", "target/CB_Backend-0.0.1-SNAPSHOT.jar"]
