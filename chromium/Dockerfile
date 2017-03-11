FROM local/archlinux:latest
MAINTAINER local

RUN pacman -Syu --quiet --noprogressbar --noconfirm \
  chromium \
  && gpasswd -a arch audio \
  && gpasswd -a arch video

USER arch
WORKDIR /home/arch
ENTRYPOINT  [ "chromium" ]
