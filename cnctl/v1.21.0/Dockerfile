FROM bash:4

ENV KUBECTL_VERSION="v1.21.0"
ENV ISTIOCTL_VERSION="1.14.5"

RUN set -ex ; \
  apk --no-cache add ca-certificates curl;
#   curl -L https://storage.googleapis.com/kubernetes-release/release/${KUBECTL_VERSION}/bin/linux/amd64/kubectl -o /usr/local/bin/kubectl; \
#   chmod +x /usr/local/bin/kubectl;

# kubectl, refer to https://kubernetes.io/docs/tasks/tools/install-kubectl-linux/#install-kubectl-binary-with-curl-on-linux
RUN curl -L https://dl.k8s.io/release/${KUBECTL_VERSION}/bin/linux/amd64/kubectl -o /usr/local/bin/kubectl; \
  chmod +x /usr/local/bin/kubectl;

# istioctl, refer to https://istio.io/latest/docs/ops/diagnostic-tools/istioctl/
RUN curl -L https://istio.io/downloadIstioctl | ISTIO_VERSION=${ISTIOCTL_VERSION} sh -; \
  mv istioctl /usr/local/bin/istioctl; \
  chmod +x /usr/local/bin/istioctl;

CMD ["sh","-c","tail -f /dev/null"]