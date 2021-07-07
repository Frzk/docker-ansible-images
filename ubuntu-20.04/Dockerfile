# Build Ubuntu 20.04 (Focal Fossa) image.

FROM ubuntu:20.04
LABEL maintainer="François KUBLER"

RUN apt-get update -yq \
  && apt-get dist-upgrade -yq \
  && apt-get install -yq --no-install-recommends \
     python3 \
     systemd \
  && apt-get clean -yq

ENTRYPOINT ["/lib/systemd/systemd"]
