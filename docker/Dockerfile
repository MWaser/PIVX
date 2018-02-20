FROM ubuntu:xenial
MAINTAINER Mark Waser <mark@artificialgeneralintelligenceinc.com>
ENV DEBIAN_FRONTEND noninteractive
WORKDIR /shared
RUN apt-get update && \
apt-get --no-install-recommends -yq install software-properties-common && \
add-apt-repository ppa:bitcoin/bitcoin 
RUN apt-get update && \
apt-get --no-install-recommends -yq install \
wget \
libdb4.8-dev \
libdb4.8++-dev \
libboost-all-dev \
libssl-dev \
libevent-dev \
locales \
git-core \
build-essential \
ca-certificates \
autoconf \
automake \
pkg-config \
libtool \
autotools-dev \
bsdmainutils \
vim \
ruby \
sudo \
rsync && \
apt-get -yq purge grub > /dev/null 2>&1 || true && \
apt-get -y dist-upgrade && \
locale-gen en_US.UTF-8 && \
update-locale LANG=en_US.UTF-8 && \
useradd -d /home/ubuntu -m -s /bin/bash ubuntu && echo "ubuntu:ubuntu" | chpasswd  && adduser ubuntu sudo && \
chown -R ubuntu.ubuntu /shared/ && \
chown -R ubuntu.ubuntu /home/ubuntu

USER ubuntu

RUN git clone -b v3.0.6 https://github.com/mwaser/pivx.git

# cd /shared/pivx
# ./autogen.sh
# ./configure  --enable-debug
# make
# sudo make install
# cd /home/ubuntu/.pivx
# rm pivx.conf
# wget https://raw.githubusercontent.com/MWaser/PIVX/3.0/docker/pivx.conf
# cd ..
# pivxd -debug
# -- close window
# docker exec -it yourcontainerhere bash
# cd /home/ubuntu/.pivx





# CMD ["v3.0.6","https://github.com/PIVX-Project/pivx.git","../pivx/contrib/gitian-descriptors/gitian-linux.yml"]
# ENTRYPOINT ["bash", "/home/ubuntu/runit.sh"]

# gitian build pivx
# git clone -b "3.0" --depth 1 "https://github.com/PIVX-Project/pivx.git" /shared/pivx
# vi /shared/ubuntu/pivx/contrib/gitian-descriptors/gitian-linux.yml
# cd /shared/gitian-builder
# ./bin/gbuild --skip-image --commit pivx="3.0" --url pivx="https://github.com/PIVX-Project/pivx.git" "../pivx/contrib/gitian-descriptors/gitian-linux.yml"

# install pivx
# cd /home/ubuntu/build
# ./autogen.sh
# ./configure
# make
# make install

# build divi  <== CURRENT GITIAN BUILD
# git clone -b "master" --depth 1 "https://cbyrdsw:Justic3123@agii.visualstudio.com/_git/DiviProject" /shared/pivx
# cd /shared/gitian-builder
# ./bin/gbuild --skip-image --commit pivx="3.0" --url pivx="https://github.com/PIVX-Project/pivx.git" "../pivx/contrib/dev-core/dev-core-linux.yml"

# install divi
# cd /home/ubuntu/build
# ./autogen.sh
# ./configure
# make
# sudo make install

# CURRENT BUILD
# git clone -b "master" --depth 1 "https://cbyrdsw:Justic3123@agii.visualstudio.com/_git/DiviProject" /shared/pivx
# cd /shared/pivx
# ./autogen.sh
# ./configure
# make
# sudo make install
# cd /home/ubuntu
# sudo wget https://raw.githubusercontent.com/PIVX-Project/PIVX/master/contrib/debian/examples/pivx.conf


#notes
# /home/ubuntu/runit.sh "master" "https://cbyrdsw:Justic3123@agii.visualstudio.com/_git/DiviProject" "../pivx/contrib/dev-core/dev-core-linux.yml"

# this line is if you want to build without wallet or gui and debug enabled
# git clone -b "master" --depth 1 "https://cbyrdsw:Justic3123@agii.visualstudio.com/_git/DiviProject" /shared/pivx
# ./configure --disable-wallet --without-gui --enable-debug
# ./configure --without-gui --enable-debug

