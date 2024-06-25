# Build Archlinux image.

FROM archlinux/archlinux:latest
LABEL maintainer="François KUBLER"

RUN pacman -Sy --noconfirm \
    archlinux-keyring \
 && pacman -Syu --noconfirm \
 && pacman -Sy --noconfirm \
    python \
    sudo

ENV ANSIBLE_USER="ansible"

RUN set -xe \
  && groupadd "${ANSIBLE_USER}" \
  && useradd -m -g "${ANSIBLE_USER}" "${ANSIBLE_USER}" \
  && mkdir -p /etc/sudoers.d \
  && echo "${ANSIBLE_USER} ALL=(ALL) NOPASSWD: ALL" > "/etc/sudoers.d/${ANSIBLE_USER}" \
  && echo "@includedir /etc/sudoers.d" >> "/etc/sudoers"

ENTRYPOINT ["/lib/systemd/systemd"]
