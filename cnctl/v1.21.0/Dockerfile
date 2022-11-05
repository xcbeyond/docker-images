FROM bash:4

ENV KUBECTL_VERSION="v1.21.0"
ENV ISTIOCTL_VERSION="1.14.5"
ENV HELM_VERSION="v3.10.0"

RUN set -ex ; \
  apk --no-cache add ca-certificates curl;

# kubectl, refer to https://kubernetes.io/docs/tasks/tools/install-kubectl-linux/#install-kubectl-binary-with-curl-on-linux
RUN curl -L https://dl.k8s.io/release/${KUBECTL_VERSION}/bin/linux/amd64/kubectl -o /usr/local/bin/kubectl; \
  chmod +x /usr/local/bin/kubectl;

# istioctl, refer to https://istio.io/latest/docs/ops/diagnostic-tools/istioctl/
RUN curl -L https://istio.io/downloadIstioctl | ISTIO_VERSION=${ISTIOCTL_VERSION} sh -; \
  cp ~/.istioctl/bin/istioctl /usr/local/bin/istioctl; \
  rm -rf ~/.istioctl/;

# helm, refer to https://helm.sh/docs/intro/install/#from-the-binary-releases
RUN wget https://get.helm.sh/helm-${HELM_VERSION}-linux-amd64.tar.gz; \
  tar -zxvf helm-${HELM_VERSION}-linux-amd64.tar.gz; \
  mv ~/linux-amd64/helm /usr/local/bin/helm; \
  chmod +x /usr/local/bin/helm; \
  rm -rf ~/linux-amd64/;

CMD ["sh","-c","tail -f /dev/null"]