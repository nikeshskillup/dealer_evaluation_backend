# Use a base image with JDK installed
FROM openjdk:11-jre-slim

# Set the working directory inside the container
WORKDIR /app

# Copy the compiled jar file from target folder
COPY target/productcomparison-0.0.1-SNAPSHOT.jar productcomparison.jar

# Run the application
CMD ["java", "-jar", "productcomparison.jar"]
