FROM library/centos:8

RUN yum install -y python2 make gsl gsl-devel gcc-c++ vim epel-release \
    && dnf -y install dnf-plugins-core \
    && dnf config-manager --set-enabled powertools \
    && yum -y install openblas-devel \
    && pip2 install networkx==1.9 numpy trueskill==0.4.5 \
    && ln -s /usr/bin/python2 /usr/bin/python

ADD breaking_cycles_in_noisy_hierarchies /app/breaking_cycles_in_noisy_hierarchies
ADD Makefile /app/breaking_cycles_in_noisy_hierarchies/agony

RUN cd /app/breaking_cycles_in_noisy_hierarchies/agony \
    && make

WORKDIR /app/breaking_cycles_in_noisy_hierarchies
