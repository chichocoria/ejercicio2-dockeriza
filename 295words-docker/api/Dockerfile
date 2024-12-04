# Build stage
FROM --platform=linux/amd64 maven:3-amazoncorretto-20 as build
WORKDIR /api
COPY . .
RUN mvn verify -DskipTests --fail-never
RUN mvn verify

# Run stage
FROM --platform=linux/amd64 amazoncorretto:20
WORKDIR /api
COPY . .
ENTRYPOINT ["java", "-Xmx8m", "-Xms8m", "-jar", "./target/words.jar"]
EXPOSE 8080