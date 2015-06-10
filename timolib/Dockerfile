# This dockerfile uses the ubuntu image to build timo library.
# The libtimo.so will be builded in /usr/local/lib.
# And timo.h will copy to /usr/local/include.
# VERSION 2 - EDITION 1
# Author: laye
# Command format: Instruction [arguments / command] ..

# Base image to use, this must be set as the first line
FROM ubuntu:14.04

# Maintainer: docker_user <docker_user at email.com> (@docker_user)
MAINTAINER laye wuch84@126.com

# Commands to update the image
RUN apt-get update && apt-get install -y \
    g++ \
    python2.7 \
    scons && \
    mkdir -p /timodocker/timolib

# copy source file
ADD timolib.tar.gz /timodocker

# build timolib
WORKDIR /timodocker/timolib
RUN scons -Q \
    && scons install \
    && rm -rf /timodocker/timolib

# reset
WORKDIR /

# env
RUN ldconfig

# Commands when creating a new container
#CMD
