# Build Debian 10 (Buster) image.

FROM debian:10
LABEL maintainer="François KUBLER"

ARG DEBIAN_FRONTEND=noninteractive

RUN apt update \
  && apt upgrade \
  && apt install -y --no-install-recommends \
     python3 \
     systemd

ENTRYPOINT ["/lib/systemd/systemd"]
