FROM   --platform=linux/amd64  registry.access.redhat.com/ubi8/go-toolset:1.18

LABEL base_image="ubi8go"

USER root

RUN yum update -yy \
	&& yum upgrade -y

USER default