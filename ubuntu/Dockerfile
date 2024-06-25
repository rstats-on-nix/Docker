FROM ubuntu:latest

LABEL org.opencontainers.image.licenses="MIT" \
      org.opencontainers.image.source="https://github.com/rstats-on-nix/Docker" \
      org.opencontainers.image.vendor="RStats on Nix" \
      org.opencontainers.image.authors="Bruno Rodrigues <bruno@brodrigues.co>, Philipp Baumann <baumann-philipp@protonmail.com>"

RUN apt update -y

RUN apt install curl -y

RUN curl --proto '=https' --tlsv1.2 -sSf -L https://install.determinate.systems/nix | sh -s -- install linux \
  --extra-conf "sandbox = false" \
  --init none \
  --no-confirm

# Adds Nix to the path, as described by the Determinate Systems installer's documentation
ENV PATH="${PATH}:/nix/var/nix/profiles/default/bin"

CMD ["/bin/sh"]