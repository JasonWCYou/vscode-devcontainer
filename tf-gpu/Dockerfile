FROM tensorflow/tensorflow:latest-gpu

RUN apt-get update && \
    apt-get -y -o Dpkg::Options::=--force-confdef -o Dpkg::Options::=--force-confnew install sudo
    
# Add user "meta" and add it to sudo group
RUN useradd -ms /bin/bash meta && \
    usermod -aG sudo meta && \
    echo "meta ALL=(ALL) NOPASSWD:ALL" >> /etc/sudoers && \
    echo "%sudo ALL=(ALL) NOPASSWD:ALL" >> /etc/sudoers

USER meta

CMD ["/bin/sh", "-c", "while true; do sleep 1000; done"]