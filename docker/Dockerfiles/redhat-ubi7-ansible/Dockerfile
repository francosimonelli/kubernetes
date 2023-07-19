FROM --platform=linux/amd64 registry.access.redhat.com/ubi7/ubi:latest
ENV LANG C.UTF-8
ENV VAR dave

LABEL base_image="ubi8jre11"

USER root

ARG RUN_JAVA_VERSION=1.3.8

RUN yum install https://dl.fedoraproject.org/pub/epel/epel-release-latest-7.noarch.rpm -y
RUN yum install hostname -y
RUN yum install ansible -y
#RUN echo -e "- name: Test ping\n  hosts: localhost\n  tasks:\n   - name: Get IP\n     shell: hostname -i" > playbook.yaml

# CMD ["echo", "hello $VAR $LANG"]
#CMD ansible-playbook playbook.yaml