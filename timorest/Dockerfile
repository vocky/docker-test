# This dockerfile uses the ubuntu image to build timorest.
# VERSION 2 - EDITION 1
# Author: laye
# Command format: Instruction [arguments / command] ..

# Base image to use, this must be set as the first line
FROM laye/timo:1.2

# Maintainer: docker_user <docker_user at email.com> (@docker_user)
MAINTAINER laye wuch84@126.com

# Commands to update the image
RUN apt-get update && apt-get install -y \
    python2.7 \
    python-pip \
    && mkdir -p /timodocker/timorest-1.0 \
    && mkdir -p /mnt/data

# copy source file
ADD timorest-1.0.tar.gz /timodocker

# pip install requirements
WORKDIR /timodocker/timorest-1.0
RUN pip install -f requirements.txt \
    && python setup.py install

WORKDIR tests
RUN pip install nose \
    && nosetests

#reset
WORKDIR /
# Commands when creating a new container
#CMD 
