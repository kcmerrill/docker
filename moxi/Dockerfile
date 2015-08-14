FROM centos:centos6

RUN yum update -y && yum install wget -y && yum clean all
RUN wget http://packages.couchbase.com/releases/2.5.0/moxi-server_2.5.0_x86_64.rpm
RUN rpm --install moxi-server_2.5.0_x86_64.rpm

EXPOSE 11211

ENTRYPOINT /etc/init.d/moxi-server start && \
while ps aux | grep moxi-server | grep -v grep ; do sleep 5; done
