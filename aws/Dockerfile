FROM ubuntu
MAINTAINER kcmerrill@gmail.com

#Giddy up
RUN apt-get update && apt-get install -y python-pip

#Install AWS-CLI along with AWS-SHELL
RUN pip install awscli aws-shell

#Setup our entrypoint
ENTRYPOINT ["aws"]

#By default, lets just configure it
CMD ["configure"]
