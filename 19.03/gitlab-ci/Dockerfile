FROM docker:19.03

ENV KUSTOMIZE_VERSION 3.8.1
ENV KUBECTL_VERSION 1.18.0

RUN apk add --no-cache \
        git \
        python3 \
        py3-pip \
        curl \
        bash \
        ca-certificates \
        openssh-client

# Install kustomize
RUN curl -L https://github.com/kubernetes-sigs/kustomize/releases/download/v${KUSTOMIZE_VER}/kustomize_${KUSTOMIZE_VERSION}_linux_amd64  -o /usr/bin/kustomize \
    && chmod +x /usr/bin/kustomize && \
    kustomize version

# Install kubectl
RUN curl -L https://storage.googleapis.com/kubernetes-release/release/v${KUBECTL_VERSION}/bin/linux/amd64/kubectl -o /usr/bin/kubectl \
    && chmod +x /usr/bin/kubectl && \
    kubectl version --client
