# Ubuntu 12.04
# version 0.1

from            ubuntu:12.04
maintainer      Andrei Neculau <andrei.neculau@gmail.com>

env             DEBIAN_FRONTEND noninteractive

# oracle-jdk7-installer (ppa:webupd8team/java)
run             echo deb http://ppa.launchpad.net/webupd8team/java/ubuntu precise main >> /etc/apt/sources.list
run             echo deb-src http://ppa.launchpad.net/webupd8team/java/ubuntu precise main >> /etc/apt/sources.list
run             apt-key adv --keyserver keyserver.ubuntu.com --recv-keys EEA14886
run             echo debconf shared/accepted-oracle-license-v1-1 select true | sudo debconf-set-selections
run             echo debconf shared/accepted-oracle-license-v1-1 seen true | sudo debconf-set-selections

# multiverse
run             sed -i 's|universe$|universe multiverse|' /etc/apt/sources.list

# Workaround for successful dist-upgrade, from https://github.com/dotcloud/docker/issues/1724
run             dpkg-divert --local --rename /usr/bin/ischroot && ln -sf /bin/true /usr/bin/ischroot

# Update
run             apt-get --fix-missing update
run             apt-get -y update
run             apt-get -y dist-upgrade
run             apt-get -y upgrade
run             apt-get clean
run             rm -rf /var/cache/apt/*

# Language
run             locale-gen en_US.UTF-8
env             LANG       en_US.UTF-8
env             LC_ALL     en_US.UTF-8

# Basic
run             apt-get install -y aptitude build-essential dialog openssl
run             apt-get install -y libssl-dev libreadline6-dev
run             apt-get install -y curl emacs git lynx mosh nano vim
