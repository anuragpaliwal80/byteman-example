# select parent image 
FROM maven:3.6.3-jdk-8 

# copy the source tree and the pom.xml to our new container
COPY Manifest.txt Manifest.txt
COPY ./ ./

# package our application code 
RUN mvn clean package 

# set the startup command to execute the jar 
CMD ["java", "-jar", "target/com.httpclient-1.0.jar"]


# #
# # Build stage
# #
# FROM maven:3.6.0-jdk-11-slim AS build
# # copy the source tree and the pom.xml to our new container 
# COPY ./ ./  

# # package our application code 
# RUN mvn clean package

# #
# # Package stage
# #
# FROM openjdk:11-jre-slim
# COPY --from=build /home/app/target/demo-0.0.1-SNAPSHOT.jar /usr/local/lib/demo.jar
# EXPOSE 8080
# ENTRYPOINT ["java","-jar","/usr/local/lib/demo.jar"]