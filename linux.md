# Linux

	tar -czvf name-of-archive.tar.gz /path/to/directory-or-file

	grep -r "some text" .

    find . -name <pattern>

## Open ports

    netstat -nat | grep LISTEN
    netstat -an | grep PORTNUMBER | grep -i listencat /etc/*-releasecat /etc/*-release

## Linux version

    cat /etc/*-release

## CPU info

    cat /proc/cpuinfo

## Write a loop:

    for ((start=1; start <= 5; start++));
        do
            wget fortunes-ui-wes.south.fe.pivotal.io
            rm index.html
            sleep 3
        done

## Stress CPU Load

    sudo apt-get install stress
    stress -cpu 2 -timeout 60

## Dockerfile syntax

    FROM openjdk:8-jdk-alpine
    VOLUME /tmp
    COPY ${LOCAL_JAR_FILE} app.jar
    ENTRYPOINT ["java","-Djava.security.egd=file:/dev/./urandom","-jar","/app.jar"]
  
## Makefile syntax

    PROJECT_ID=$(shell gcloud config list project --format=flattened | awk 'FNR == 1 {print $$2}')
    GCLOUD_USER=$(shell gcloud config get-value core/account)

    create-cluster:
        gcloud container --project "$(PROJECT_ID)" clusters create "$(CLUSTER_NAME)" --zone "$(ZONE)" 
        kubectl create clusterrolebinding cluster-admin-binding --clusterrole=cluster-admin --user=$(GCLOUD_USER)
    push:
        gcloud auth configure-docker
        docker push gcr.io/$(PROJECT_ID)/istiotest:1.0

## Linux Programs

### Editor - Visual Studio

    https://code.visualstudio.com/download

### Screencast, Screenshot, Screen Recording - Kazam

    sudo apt-get install kazam

### Photo editing - Gimp

###
