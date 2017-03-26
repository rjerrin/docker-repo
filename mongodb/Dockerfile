#pull centos image

FROM centos:centos6

#add mongodb repo
ADD ./mongodb.repo  /etc/yum.repos.d/mongodb.repo
#update yum repository and clean cache
RUN yum  update -y
#install packages
RUN yum install  -y  mongo-10gen mongo-10gen-server python-setuptools
RUN easy_install supervisor

#add supervisord.conf for running mongodb
ADD supervisord.conf /etc/


#Expose ports for mongodb

EXPOSE  27017

#Run supervisord to start tomcat and mongodb

CMD   ["supervisord", "-n"]


