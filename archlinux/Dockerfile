# Build Archlinux image.

FROM archlinux/archlinux:latest
LABEL maintainer="François KUBLER"

RUN pacman -Sy --noconfirm \
    archlinux-keyring \
 && pacman -Syu --noconfirm \
 && pacman -Sy --noconfirm \
    python

ENTRYPOINT ["/lib/systemd/systemd"]
