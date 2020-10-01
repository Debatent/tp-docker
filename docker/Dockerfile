FROM java:8
FROM gradle AS build
COPY --chown=gradle:gradle . /home/DevOpsTPApp/tp-docker/src
WORKDIR /docker
RUN gradle build --no-daemon

#COPY tp-docker-1.0.0.jar tp-docker-1.0.0.jar
ENV url="127.0.0.1:5432/tp_devops"
ENV username="tp_dvops"
ENV password="tp_devops"
EXPOSE 8080

ENTRYPOINT java -Ddatabase.url=$url -Ddatabase.username=$username -Ddatabase.password=$password -jar tp-docker-1.0.0.jar
