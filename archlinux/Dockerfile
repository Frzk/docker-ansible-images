# Build Archlinux image.

FROM archlinux/archlinux:latest
LABEL maintainer="François KUBLER"

# TEMP-FIX until hub.docker.com fix their sh*t.
#RUN patched_glibc=glibc-linux4-2.33-4-x86_64.pkg.tar.zst && \
# curl -LO "https://repo.archlinuxcn.org/x86_64/$patched_glibc" && \
# bsdtar -C / -xvf "$patched_glibc"
# /TEMP-FIX until hub.docker.com fix their sh*t.

RUN pacman -Sy --noconfirm \
    archlinux-keyring \
 && pacman -Syu --noconfirm \
 && pacman -Sy --noconfirm \
    python

ENTRYPOINT ["/lib/systemd/systemd"]
