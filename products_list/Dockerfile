# Use an official Maven image to build the application
FROM maven:4.0.0-openjdk-17-slim AS build
 
# Set the working directory for the build stage
WORKDIR /app
 
# Copy the Maven project files into the container
COPY pom.xml ./
COPY src ./src
 
# Run Maven to clean and package the application
RUN mvn clean package
 
# Use an official OpenJDK runtime as the base image for the final stage
FROM openjdk:17-jdk-slim
 
# Set the working directory for the runtime stage
WORKDIR /java-docker
 
# Copy the built WAR file from the build stage
COPY --from=build /app/target/product_list-0.0.1-SNAPSHOT.war product_list.war
 
# Copy the products.json file into the runtime container
COPY products.json products.json
 
# Command to run the application
CMD ["java", "-jar", "product_list.war"]
