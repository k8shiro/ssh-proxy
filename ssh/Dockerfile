FROM sickp/alpine-sshd:latest
RUN passwd -d root
RUN mkdir -p /root/.ssh
WORKDIR /root/.ssh
RUN ssh-keygen -f id_rsa -t rsa -N ''
RUN cat id_rsa.pub >> authorized_keys
RUN chmod 0600 authorized_keys
RUN echo "Port 80" >> /etc/ssh/sshd_config
