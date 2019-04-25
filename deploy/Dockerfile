FROM alpine:latest
RUN apk --no-cache add \
    bash \
    git \
    jq \
    curl \
    python3 \
    py3-cffi \
    python3-dev \
    libffi-dev \
    openssl-dev \
    gcc \
    make \
    musl-dev \
    openssh-client \
    rsync
RUN pip3 --no-cache-dir install fabric patchwork jinja2 dataclasses
RUN apk --no-cache del python3-dev libffi-dev openssl-dev gcc make musl-dev
COPY curl-vault /usr/local/bin/curl-vault
COPY vault-ssh-keysign /usr/local/bin/vault-ssh-keysign
CMD sh
