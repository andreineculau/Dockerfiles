# Erlang R16B03-1
# version 0.1

from            andreineculau/ubuntu-12.04
maintainer      Andrei Neculau <andrei.neculau@gmail.com>

add             https://github.com/erlang/otp/archive/OTP_R16B03-1.tar.gz /tmp

workdir         /tmp
run             tar -xvzf OTP_R16B03-1.tar.gz

workdir         /tmp/otp-OTP_R16B03-1
run             ./configure
run             make
run             make install

workdir         /tmp
run             rm     OTP_R16B03-1.tar.gz
run             rm -rf otp-OTP_R16B03-1
