ubuntu-core:12.04.5
============

Dockerfile:

    FROM scratch
    MAINTAINER Frank Lemanschik
    ADD ./ubuntu-core-12.04.5-core-amd64.tar.gz /
    ENV LC_ALL C
    ENV DEBIAN_FRONTEND noninteractive
    RUN echo 'APT::Install-Recommends "0"; \n\
    APT::Get::Assume-Yes "true"; \n\
    APT::Get::force-yes "true"; \n\
    APT::Install-Suggests "0";' > /etc/apt/apt.conf.d/01buildconfig
