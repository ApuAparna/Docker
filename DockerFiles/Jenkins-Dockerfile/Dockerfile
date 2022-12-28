# Installing Java And Jenkins Using Dockerfile
FROM ubuntu

WORKDIR ./jenkins

COPY ./Dockerfile  ./

RUN apt-get -y update \
    &&  apt-get -y upgrade

RUN apt-get -y  install default-jdk

RUN java --version

RUN apt-get -y install wget

RUN apt-get -y  update && apt-get install -y gnupg

RUN wget -q -O - https://pkg.jenkins.io/debian-stable/jenkins.io.key | apt-key add -

RUN sh -c 'echo deb https://pkg.jenkins.io/debian-stable binary/ > \
/etc/apt/sources.list.d/jenkins.list'

RUN apt-get -y update \
    &&apt-get -y install jenkins

EXPOSE 8080

ENTRYPOINT ["jenkins"]
