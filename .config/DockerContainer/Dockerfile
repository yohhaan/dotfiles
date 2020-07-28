FROM ubuntu:latest
# Install tools
RUN apt-get update && \
    apt-get install software-properties-common git gcc make python gdb build-essential autoconf valgrind man nano curl wget -y && \
    apt-get install libtool pkg-config libcurl4-gnutls-dev libgcrypt-dev -y && \
    apt-get clean autoclean && \
    apt-get autoremove -y

# Enable GDB
RUN mkdir -p /root
RUN touch /root/.gdbinit && \
    echo "set auto-load safe-path /" >> /root/.gdbinit
# Alias nano
RUN echo "alias nano=\"nano -T 4 -i -E\"" >> /root/.bashrc
EXPOSE 6666
VOLUME "/root/project"
WORKDIR "/root/project"
