FROM ubuntu:16.04
MAINTAINER "Tamas Molnar - <tmolnar0831@gmail.com>"
ENV container docker
RUN (cd /lib/systemd/system/sysinit.target.wants/; for i in *; do [ $i == \
      systemd-tmpfiles-setup.service ] || rm -f $i; done); \
      rm -f /lib/systemd/system/multi-user.target.wants/*;\
      rm -f /etc/systemd/system/*.wants/*;\
      rm -f /lib/systemd/system/local-fs.target.wants/*; \
      rm -f /lib/systemd/system/sockets.target.wants/*udev*; \
      rm -f /lib/systemd/system/sockets.target.wants/*initctl*; \
      rm -f /lib/systemd/system/basic.target.wants/*;\
      rm -f /lib/systemd/system/anaconda.target.wants/*;
RUN apt-get -y update
RUN apt-get -y install ansible
VOLUME [ "/sys/fs/cgroup" ]
CMD ["/sbin/init"]
