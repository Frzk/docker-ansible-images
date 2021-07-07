# Build Ubuntu 16.04 (Xenial Xerus) image.

FROM ubuntu:16.04
LABEL maintainer="François KUBLER"

RUN apt-get update -yq \
  && apt-get dist-upgrade -yq \
  && apt-get install -yq --no-install-recommends \
     python3 \
     systemd \
  && apt-get clean -yq

ENTRYPOINT ["/lib/systemd/systemd"]
