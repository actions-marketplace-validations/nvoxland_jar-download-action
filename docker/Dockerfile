## Create a base docker image which contains all the maven plugins pre-downloaded from maven central

FROM maven:3.8.6-eclipse-temurin-17-focal

COPY pom.xml /builder.pom.xml

## Have to specify an artifact to include as the dependency so maven doesn't complain. Picked one already included by dependency-plugin
RUN mvn -B -f /builder.pom.xml -s /usr/share/maven/ref/settings-docker.xml -Dartifact.artifactId=commons-io -Dartifact.groupId=commons-io -Dartifact.version=2.11.0 dependency:go-offline
