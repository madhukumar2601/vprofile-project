FROM openjdk:11 as BUILD_IMAGE
RUN apt update && apt install maven
RUN git clone https://github.com/devopshydclub/vprofile-project.git
RUN cd vprofile-project && git checkout docker && mvn install
LABEL "project="vprofile"
LABEL "Author"="imran"

FROM tomcat:9-jre11
RUN rm -rf/usr/local/tomcat/webapps/*
copy --from=BUILD_IMAGE vprofile-project/target/vprofile-v2.war /usr/local/tomcat/webapps/RC

EXPOSE 8080
CMD["catalina.sh", "run"]
WORKDIR /usr/local/tomcat
VOLUME /usr/local/tomcat/webapps