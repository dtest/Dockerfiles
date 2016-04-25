FROM dtestops/base
MAINTAINER downey@pythian.com

ENV VAULT_VERSION=0.5.2

ADD hashicorp.gpg /tmp/hashicorp.gpg

RUN cd /tmp \
  && curl -SLO "https://releases.hashicorp.com/vault/$VAULT_VERSION/vault_${VAULT_VERSION}_linux_amd64.zip" \
  && curl -SLO "https://releases.hashicorp.com/vault/$VAULT_VERSION/vault_${VAULT_VERSION}_SHA256SUMS" \
  && curl -SLO "https://releases.hashicorp.com/vault/$VAULT_VERSION/vault_${VAULT_VERSION}_SHA256SUMS.sig"

RUN cd /tmp \
  && gpg --import hashicorp.gpg \
  && gpg --verify vault_"$VAULT_VERSION"_SHA256SUMS.sig vault_"$VAULT_VERSION"_SHA256SUMS \
  && grep " vault_${VAULT_VERSION}_linux_amd64.zip\$" vault_"$VAULT_VERSION"_SHA256SUMS | sha256sum -c - \
  && unzip vault_${VAULT_VERSION}_linux_amd64.zip \
  && mv vault /usr/local/bin/ \
  && rm -f vault_"$VAULT_VERSION"_linux_amd64.zip vault_"$VAULT_VERSION"_SHA256SUMS vault_"$VAULT_VERSION"_SHA256SUMS.sig

EXPOSE 8200

ENTRYPOINT [ "vault" ]
CMD [ "server", "-dev" ]
