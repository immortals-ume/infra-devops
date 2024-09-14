# Use an official Ubuntu base image
FROM ubuntu:20.04

# Metadata about the image
LABEL authors="kaish"

# Install required packages: Maven, JDK, and other dependencies
RUN apt-get update && \
    apt-get install -y maven openjdk-11-jdk curl && \
    apt-get clean

# Set environment variables for Java and Maven
ENV JAVA_HOME=/usr/lib/jvm/java-11-openjdk-amd64
ENV MAVEN_HOME=/usr/share/maven
ENV PATH=${MAVEN_HOME}/bin:${JAVA_HOME}/bin:${PATH}

# Copy your Maven project (if you have a local project, uncomment this)
# COPY . /usr/src/app

# Set the working directory to where your Maven project is located
WORKDIR /usr/src/app

# Run Maven package when the container starts
ENTRYPOINT ["mvn", "clean", "install"]

# You can alternatively use "CMD" to allow overriding entrypoint if needed
# CMD ["mvn", "clean", "install"]
