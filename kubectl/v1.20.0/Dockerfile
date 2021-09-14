FROM bash:4

ENV KUBE_LATEST_VERSION="v1.20.0"

RUN set -ex ; \
  apk --no-cache add ca-certificates curl; \
  curl -L https://storage.googleapis.com/kubernetes-release/release/${KUBE_LATEST_VERSION}/bin/linux/amd64/kubectl -o /usr/local/bin/kubectl; \
  chmod +x /usr/local/bin/kubectl; 

CMD ["sh","-c","tail -f /dev/null"]