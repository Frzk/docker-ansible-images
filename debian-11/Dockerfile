# Build Debian 11 (Bullseye) image.

FROM debian:bullseye-slim
LABEL maintainer="François KUBLER"

ARG DEBIAN_FRONTEND=noninteractive

RUN apt-get update -yq \
  && apt-get dist-upgrade -yq \
  && apt-get install -yq --no-install-recommends \
     python3 \
     systemd \
  && apt-get clean -yq

ENTRYPOINT ["/lib/systemd/systemd"]
