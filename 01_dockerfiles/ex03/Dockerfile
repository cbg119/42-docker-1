FROM ubuntu

RUN apt-get update -y && apt-get -y upgrade && apt-get -y install wget openssh-server \
	ca-certificates postfix

RUN wget https://packages.gitlab.com/install/repositories/gitlab/gitlab-ce/script.deb.sh && \
	chmod 777 ./script.deb.sh && \
	./script.deb.sh

RUN apt-get install -y tzdata gitlab-ce

EXPOSE 443 80 22

RUN gitlab-ctl reconfigure
