FROM local/archlinux:latest
MAINTAINER local

RUN pacman -Syu --quiet --noprogressbar --noconfirm \
  && sudo -u installer yaourt -S pithos \
  && gpasswd -a arch audio

USER arch
WORKDIR /home/arch
ENTRYPOINT [ "pithos" ]
