FROM bash:4

ENV KUBECTL_VERSION="v1.21.0"
ENV ISTIOCTL_VERSION="1.14.5"

RUN set -ex ; \
  apk --no-cache add ca-certificates curl;

# kubectl, refer to https://kubernetes.io/docs/tasks/tools/install-kubectl-linux/#install-kubectl-binary-with-curl-on-linux
RUN curl -L https://dl.k8s.io/release/${KUBECTL_VERSION}/bin/linux/amd64/kubectl -o /usr/local/bin/kubectl; \
  chmod +x /usr/local/bin/kubectl;

# istioctl, refer to https://istio.io/latest/docs/ops/diagnostic-tools/istioctl/
RUN curl -L https://istio.io/downloadIstioctl | ISTIO_VERSION=${ISTIOCTL_VERSION} sh -;

CMD ["sh","-c","tail -f /dev/null"]