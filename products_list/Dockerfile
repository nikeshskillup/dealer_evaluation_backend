# Use an official OpenJDK image as the base image
FROM openjdk:17-jdk-slim

# Set the working directory inside the container
WORKDIR /app

# Copy the Maven wrapper files
COPY mvnw mvnw.cmd ./
COPY .mvn .mvn

# Copy the Maven pom.xml file
COPY pom.xml ./

# Download the Maven dependencies
RUN ./mvnw dependency:go-offline

# Copy the source code and resources
COPY src /app/src
COPY src/main/resources/products.json /app/src/main/resources/products.json

# Build the application (skip tests to speed up build)
RUN ./mvnw clean package -DskipTests

# Copy the built WAR file into the container
COPY target/products_list-0.0.1-SNAPSHOT.war app.war

# Expose the port the application will run on
EXPOSE 8080

# Command to run the application
ENTRYPOINT ["java", "-jar", "app.war"]
