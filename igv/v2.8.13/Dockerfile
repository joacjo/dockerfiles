# IGV
# http://software.broadinstitute.org/software/igv/
# v2.8.13

# base image: Ubuntu
FROM ubuntu:20.04

# File Author / Maintainer
LABEL maintainer="frederic.lemoine@pasteur.fr"

ENV VERSION=1.11

ENV PATH $PATH:/usr/local/IGV_2.8.13
ENV DEBIAN_FRONTEND="noninteractive" TZ="Europe/Paris"

RUN apt-get update --fix-missing \
    && apt-get install -y unzip default-jdk xvfb wget xorg \
    && cd /usr/local/ \
    && wget https://data.broadinstitute.org/igv/projects/downloads/2.8/IGV_2.8.13.zip \
    && unzip IGV_2.8.13.zip \
    && cd IGV_2.8.13 \
    && mv igv.sh igv \
    && apt-get remove -y unzip \
    && apt-get autoremove -y \
    && apt-get clean \
    && rm -rf /var/lib/apt/lists/* \
    && mkdir /pasteur

ENTRYPOINT ["/usr/local/IGV_Linux_2.8.13/igv"]
