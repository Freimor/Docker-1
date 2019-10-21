FROM ubuntu

RUN apt-get update && \
    apt-get upgrade -y && \
    apt-get install wget openssh-server ca-certificates postfix -y && \
    wget https://packages.gitlab.com/install/repositories/gitlab/gitlab-ce/script.deb.sh && chmod 777 script.deb.sh && ./script.deb.sh && \
    apt-get install tzdata gitlab-ce -y

EXPOSE 443 80 22

ENTRYPOINT (/opt/gitlab/embedded/bin/runsvdir-start &) && sleep 2 && gitlab-ctl reconfigure && gitlab-ctl tail
# docker run -it --rm -p 8080:80 -p 8022:22 -p 8443:443 --privileged ex03
# The --privileged flag gives all capabilities to the container,
# and it also lifts all the limitations enforced by the device cgroup controller.
# In other words, the container can then do almost everything that the host can do.
# This flag exists to allow special use-cases, like running Docker within Docker.