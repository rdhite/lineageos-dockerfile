FROM ubuntu:16.04

### PREREQUISITE PACKAGES ###
RUN apt-get update && apt-get install -y openjdk-8-jdk

#The three installs commands  below are inspired by http://forum.xda-developers.com/showthread.php?t=2464683 
RUN apt-get install -y sudo git lzop ccache gnupg flex bison gperf \
build-essential zip curl zlib1g-dev libc6-dev \
lib32ncurses5 lib32z1 lib32ncurses5-dev x11proto-core-dev \
lib32z-dev \
libgl1-mesa-dev g++-multilib tofrodos python-markdown \
libxml2-utils xsltproc readline-common libreadline6-dev libreadline6 \
libncurses5-dev lib32readline6 \
libreadline-dev bzip2 libbz2-dev \
libbz2-1.0 libghc-bzlib-dev libsdl1.2-dev libesd0-dev \
squashfs-tools pngcrush schedtool python gcc g++ cpp maven && \
rm -rf /var/cache/*

#Took out gcc and g++ 4.8 since they don't seem to be necessary
#RUN apt-get install -y gcc-4.8 g++-4.8

#These packages are not available in ubuntu 16.04
#RUN apt-get install -y zlib1g-dev:i386 lib32bz2-1.0 libx11-dev:i386 \
#libreadline6-dev:i386 libgl1-mesa-glx:i386 mingw32 \
#lib32readline-gplv2-dev lib32readline5 libreadline6-dev:i386 \
#libreadline6:i386 lib32bz2-dev libwxgtk2.8-dev \

### REPO ###
RUN mkdir /home/bin && curl http://commondatastorage.googleapis.com/git-repo-downloads/repo > /home/bin/repo && chmod a+x /home/bin/repo

### LineageOS ###
RUN mkdir /home/LineageOS && cd /home/LineageOS && /home/bin/repo init -u git://github.com/LineageOS/android.git -b cm-14.1
VOLUME /home/LineageOS
