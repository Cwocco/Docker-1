FROM ubuntu

# Dependencies
RUN apt-get update
RUN apt-get install -y curl openssh-server ca-certificates
RUN sudo apt-get install -y postfix

# GitLab Packages
RUN curl https://packages.gitlab.com/install/repositories/gitlab/gitlab-ee/script.deb.sh
RUN bash script.deb.sh

RUN sudo EXTERNAL_URL="http://gitlab.example.com" apt-get install gitlab-ee