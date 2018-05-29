# DO NOT ALTER OR REMOVE COPYRIGHT NOTICES OR THIS HEADER.
#
# Copyright (c) 2015 Oracle and/or its affiliates. All rights reserved.
#
FROM oraclelinux:7-slim

ARG OPENJDK_DOWNLOAD_URL=https://download.java.net/java/GA/jdk10/10.0.1/fb4372174a714e6b8c52526dc134031e/10/openjdk-10.0.1_linux-x64_bin.tar.gz

RUN yum install -y tar gzip && \
    rm -rf /var/cache/yum

RUN curl -o openjdk.tar.gz ${OPENJDK_DOWNLOAD_URL} && \
    mkdir -p /usr/java && \
    cd /usr/java && \
    tar zxvf /openjdk.tar.gz && \
    ln -s jdk* latest && \
    rm /openjdk.tar.gz

ENV JAVA_HOME /usr/java/latest
ENV PATH ${PATH}:${JAVA_HOME}/bin

WORKDIR /

CMD ["java", "-version"]
