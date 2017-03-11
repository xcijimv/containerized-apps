FROM local/archlinux:latest
MAINTAINER local

RUN pacman -Syu --quiet --noprogressbar --noconfirm \
  ttf-dejavu \
  ttf-liberation \
  noto-fonts \
  adobe-source-sans-pro-fonts \
  adobe-source-code-pro-fonts \
  firefox \
  && gpasswd -a arch audio \
  && gpasswd -a arch video \
  && install -o arch -g arch -m 700 -d /home/arch/.config \
  && install -o arch -g arch -m 700 -d /home/arch/Downloads

RUN sudo -u installer yaourt -Rsn -dd --noconfirm dconf gtk2

USER arch
WORKDIR /home/arch
ENTRYPOINT [ "firefox" ]
