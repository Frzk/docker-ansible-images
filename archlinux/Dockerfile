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
ENV SUDO_GROUP="sudoers"

RUN set -xe \
  && groupadd "${ANSIBLE_USER}" \
  && groupadd -r "${SUDO_GROUP}" \
  && useradd -m -g "${ANSIBLE_USER}" "${ANSIBLE_USER}" \
  && usermod -a -G "${SUDO_GROUP}" "${ANSIBLE_USER}" \
  && mkdir -p /etc/sudoers.d \
  && echo "%${SUDO_GROUP} ALL=(ALL) NOPASSWD:ALL" > "/etc/sudoers.d/${SUDO_GROUP}" \
  && echo "@includedir /etc/sudoers.d" >> "/etc/sudoers"

ENTRYPOINT ["/lib/systemd/systemd"]
