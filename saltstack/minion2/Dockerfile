FROM debian:stretch

RUN apt update && apt install -y curl bash

RUN curl -o /bootstrap -Ls https://bootstrap.saltstack.com
RUN bash /bootstrap -PX -c /tmp
ADD minion2 /etc/salt/minion
ADD minion2.pem /etc/salt/pki/minion/minion.pem
ADD minion2.pub /etc/salt/pki/minion/minion.pub

RUN echo 'tmpfs /run tmpfs rw,nosuid,nodev,mode=755 0 0' >> /etc/fstab

CMD ["/usr/bin/salt-minion"]
