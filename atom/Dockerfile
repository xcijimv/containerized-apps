FROM local/archlinux:latest
MAINTAINER local

RUN pacman -Syu --quiet --noprogressbar --noconfirm
  ttf-dejavu \
  && sudo -u installer yaourt -S atom-editor-bin

USER arch
WORKDIR /home/arch
ENTRYPOINT [ "atom" ]
