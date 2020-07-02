FROM alpine:latest
RUN apk --no-cache add \
    bash \
    git \
    jq \
    curl \
    python3 \
    py3-pip \
    py3-cffi \
    python3-dev \
    libffi-dev \
    openssl-dev \
    gcc \
    make \
    musl-dev \
    openssh-client \
    rsync
RUN pip3 --no-cache-dir install jinja2 dataclasses requests
RUN apk --no-cache del python3-dev libffi-dev openssl-dev gcc musl-dev
RUN curl -sL https://sentry.io/get-cli/ | bash
COPY curl-vault /usr/local/bin/curl-vault
COPY vault-ssh-keysign /usr/local/bin/vault-ssh-keysign
COPY vault-ssh-agent /usr/local/bin/vault-ssh-agent
CMD sh
