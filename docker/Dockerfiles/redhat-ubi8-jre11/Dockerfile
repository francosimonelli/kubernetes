FROM --platform=linux/amd64 registry.access.redhat.com/ubi8/openjdk-11-runtime:1.15
ENV LANG C.UTF-8

LABEL base_image="ubi8jre11"

USER root

ARG RUN_JAVA_VERSION=1.3.8

RUN microdnf -y update && \
    microdnf clean all && \
    usermod -u 1000 jboss && cp /etc/passwd /home/jboss/passwd && \
    chown -R 1000:0 $HOME && \
    chmod ug+rwX /home/jboss /home/jboss/passwd && \
    useradd www-data && \
    mkdir -p /deployments && \
    chown 1000 /deployments && \
    chmod "g+rwX" /deployments && \
    chown 1000:root /deployments && \
    curl https://repo1.maven.org/maven2/io/fabric8/run-java-sh/${RUN_JAVA_VERSION}/run-java-sh-${RUN_JAVA_VERSION}-sh.sh -o /deployments/run-java.sh && \
    chown 1000 /deployments/run-java.sh && \
    chmod 555 /deployments/run-java.sh && \
    echo "securerandom.source=file:/dev/urandom" >> /etc/alternatives/jre/lib/security/java.security

USER jboss

WORKDIR /deployments