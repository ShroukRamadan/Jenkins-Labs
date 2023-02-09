# FROM ubuntu
# USER root
# RUN mkdir -p jenkins_home && chmod 777 jenkins_home
# RUN apt-get update -qq
# RUN apt-get install openjdk-8-jdk openssh-server -qq
# RUN useradd -ms /bin/bash jenkins 

# #------------------

# RUN apt-get update -qq \
#     && apt-get install -qqy apt-transport-https ca-certificates curl gnupg2 software-properties-common

# RUN curl -fsSL https://download.docker.com/linux/debian/gpg | apt-key add -

# RUN add-apt-repository \
#    "deb [arch=amd64] https://download.docker.com/linux/debian \
#    $(lsb_release -cs) \
#    stable"

# RUN apt-get update  -qq \
#     && apt-get -y install docker-ce

# RUN usermod -aG  docker jenkins 

# USER jenkins

# WORKDIR  /jenkins_home

# CMD [ "/bin/bash" ]


FROM ubuntu
USER root
RUN mkdir -p jenkins_home
RUN chmod 777 jenkins_home
RUN apt-get update -qq
RUN apt-get install openjdk-8-jdk -qq

#install ssh server
RUN apt-get install openssh-server -qq
RUN useradd -ms /bin/bash jenkins

#install docker client
RUN apt-get update -qq
RUN apt-get install -qq apt-transport-https ca-certificates  curl  gnupg lsb-release
RUN mkdir -p /etc/apt/keyrings
RUN curl -fsSL https://download.docker.com/linux/ubuntu/gpg | gpg --dearmor -o /etc/apt/keyrings/docker.gpg
RUN echo \
  "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.gpg] https://download.docker.com/linux/ubuntu \
  $(lsb_release -cs) stable" | tee /etc/apt/sources.list.d/docker.list > /dev/null

RUN apt-get update  -qq \
    && apt-get -y install docker-ce
    
RUN usermod -aG docker jenkins 
USER jenkins
WORKDIR /jenkins_home
CMD [ "/bin/bash" ]