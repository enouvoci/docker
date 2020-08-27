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
RUN curl -O -L https://github.com/kubernetes-sigs/kustomize/releases/download/kustomize%2Fv${KUSTOMIZE_VERSION}/kustomize_v${KUSTOMIZE_VERSION}_linux_amd64.tar.gz \
    && tar xzf ./kustomize_v${KUSTOMIZE_VERSION}_linux_amd64.tar.gz \
    && rm ./kustomize_v${KUSTOMIZE_VERSION}_linux_amd64.tar.gz \
    && mv ./kustomize /usr/bin/kustomize && chmod +x /usr/bin/kustomize \
    && kustomize version

# Install kubectl
RUN curl -L https://storage.googleapis.com/kubernetes-release/release/v${KUBECTL_VERSION}/bin/linux/amd64/kubectl -o /usr/bin/kubectl \
    && chmod +x /usr/bin/kubectl && \
    kubectl version --client
