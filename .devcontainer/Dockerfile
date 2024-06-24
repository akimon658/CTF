FROM ubuntu:22.04

RUN apt-get update && apt-get upgrade -y
RUN apt-get install binutils build-essential curl gdb git python3 sudo -y
RUN groupadd --gid 1000 user \
    && useradd --uid 1000 --gid 1000 -m user \
    && echo user ALL=\(root\) NOPASSWD:ALL > /etc/sudoers.d/user \
    && chmod 0440 /etc/sudoers.d/user

USER user

RUN git clone https://github.com/pwndbg/pwndbg.git ~/pwndbg \
    && cd ~/pwndbg \
    && ./setup.sh

CMD [ "/bin/bash" ]
