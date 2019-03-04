FROM centos:5.11

RUN rm /etc/yum.repos.d/libselinux.repo \
 && sed -i '/mirrorlist/d' /etc/yum.repos.d/CentOS-Base.repo \
 && sed -i 's_#baseurl_baseurl_' /etc/yum.repos.d/CentOS-Base.repo \
 && sed -i 's_mirror.centos.org/centos_vault.centos.org_' /etc/yum.repos.d/CentOS-Base.repo \
 && sed -i 's_$releasever_5.11_' /etc/yum.repos.d/CentOS-Base.repo \
 && yum downgrade -y libselinux

CMD /bin/bash

ARG BUILD_DATE
ARG VCS_REF
LABEL org.label-schema.build-date=$BUILD_DATE \
      org.label-schema.vcs-url="https://github.com/brimstone/docker-centos" \
      org.label-schema.vcs-ref=$VCS_REF \
      org.label-schema.schema-version="1.0.0-rc1"
