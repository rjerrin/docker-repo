#pull centos image

FROM centos:centos7


#Add repository for python-2.7

#update yum repository and clean cache
RUN yum -y update
#install packages
RUN yum install  --nogpgcheck -y  epel-release
RUN yum install --nogpgcheck  -y  python27 python2-pip
RUN useradd -ms /bin/bash slackbot
RUN mkdir -pv /opt/slackbot 
RUN chown -R slackbot:slackbot /opt/slackbot
VOLUME  [ "/opt/slackbot" ] 

USER slackbot
RUN pip install --user slackclient
RUN pip install --user pyvmomi
#WORKDIR  /opt/slackbot 
#ADD  ./slack-test.py  /opt/slackbot/slack-test.py

#CMD ["python", "/opt/slackbot/slack-test.py"]
