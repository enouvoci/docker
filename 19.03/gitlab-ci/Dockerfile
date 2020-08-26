FROM docker:19.03

ENV KUBECTL_VERSION $(curl -s https://storage.googleapis.com/kubernetes-release/release/latest.txt)

RUN apk add --no-cache \
        git \
        python3 \
        py3-pip \
        curl \
        bash \
        ca-certificates \
        openssh-client

# Install kubectl
RUN curl -L https://storage.googleapis.com/kubernetes-release/release/v${KUBECTL_VERSION}/bin/linux/amd64/kubectl -o /usr/bin/kubectl \
    && chmod +x /usr/bin/kubectl && \
    kubectl version --client
