FROM centos:latest

RUN ["yum", "install", "-y", "openssh-clients", "openssh-server"]
RUN ["mkdir", "/var/run/sshd"]
RUN echo 'root:screencast' | chpasswd
RUN sed -i 's/PermitRootLogin prohibit-password/PermitRootLogin yes/' /etc/ssh/sshd_config

# SSH login fix. Otherwise user is kicked off after login
RUN sed 's@session\s*required\s*pam_loginuid.so@session optional pam_loginuid.so@g' -i /etc/pam.d/sshd

ENV NOTVISIBLE "in users profile"
RUN echo "export VISIBLE=now" >> /etc/profile

# generate key gen 
RUN ssh-keygen -t rsa -f /etc/ssh/ssh_host_rsa_key
RUN ssh-keygen -t ecdsa -f /etc/ssh/ssh_host_ecdsa_key
RUN ssh-keygen -t ed25519 -f /etc/ssh/ssh_host_ed25519_key
#RUN sed -i 's/UsePAM yes/UsePAM no/g' /etc/ssh/sshd_config
EXPOSE 22
ENTRYPOINT ["/usr/sbin/sshd", "-D"]