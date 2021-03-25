FROM library/centos:8

RUN yum install -y python2 make gsl gsl-devel gcc-c++ vim \
    && dnf -y install dnf-plugins-core \
    && dnf -y install https://dl.fedoraproject.org/pub/epel/epel-release-latest-8.noarch.rpm \
    && dnf config-manager --set-enabled PowerTools \
    && yum -y install openblas-devel \
    && pip2 install networkx==1.9 numpy trueskill==0.4.5

ADD breaking_cycles_in_noisy_hierarchies /app/breaking_cycles_in_noisy_hierarchies
ADD Makefile /app/breaking_cycles_in_noisy_hierarchies/agony

RUN cd /app/breaking_cycles_in_noisy_hierarchies/agony \
    && ls -alhtr \
    && make

WORKDIR /app/breaking_cycles_in_noisy_hierarchies
