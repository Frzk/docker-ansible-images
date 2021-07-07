# Build Ubuntu 18.04 (Bionic Beaver) image.

FROM ubuntu:18.04
LABEL maintainer="François KUBLER"

RUN apt-get update -yq \
  && apt-get dist-upgrade -yq \
  && apt-get install -yq --no-install-recommends \
     python3 \
     systemd \
  && apt-get clean -yq

ENTRYPOINT ["/lib/systemd/systemd"]
