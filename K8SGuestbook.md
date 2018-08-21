## Build a cluster
    gcloud container clusters create mycluster --num-nodes=3

## Go to your guestbook service directory and build it

    mvn package

## Put this Docker file in the guestbook service directory

    FROM openjdk:8-jdk-alpine
    VOLUME /tmp
    COPY target/guestbook-0.0.1-SNAPSHOT.war app.jar
    ENTRYPOINT ["java","-Djava.security.egd=file:/dev/./urandom","-jar","/app.jar"]

## Build a container
    docker build -t gcr.io/{your project}/guestbook:1.0 .

## Push the container to a registry
    gcloud docker -- push gcr.io/{your project}/guestbook:1.0

## Set up authentication

    gcloud container clusters get-credentials mycluster 
    gcloud auth application-default login

## Deploy the image

    kubectl run mycluster --image=gcr.io/{your project}/guestbook:1.0 --replicas=3 --port 8080

## Put a load balancer and external IP in front of it

    kubectl expose deployment mycluster --type=LoadBalancer --port 8080

## Get the IP

    kubectl get service

## Verify the service

    In a browser, visit the EXTERNAL IP of the service at port 8080