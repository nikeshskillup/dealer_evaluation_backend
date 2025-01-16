# Use an official OpenJDK image as the base image
FROM openjdk:17-jdk-slim
 
# Set the working directory inside the container
WORKDIR /app
 
# Copy the built JAR file into the container
COPY target/products_list-0.0.1-SNAPSHOT.war app.war
 
# Expose the port the application will run on
EXPOSE 5000
 
# Command to run the application
ENTRYPOINT ["java", "-jar", "app.war"]