FROM ubuntu

ENV ROOT_PASSWD 123
# image with node env
RUN apt update && apt install openssh-server -y && mkdir -p /var/run/sshd  && sed -i "s/#PermitRootLogin prohibit-password/PermitRootLogin yes/" /etc/ssh/sshd_config && sed -i 's/#PermitEmptyPasswords no/PermitEmptyPasswords yes/' /etc/ssh/sshd_config && echo 'root:123' |chpasswd

EXPOSE 22
CMD ["/usr/sbin/sshd", "-D"]