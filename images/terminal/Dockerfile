FROM fedora

USER root

ENV GOPATH=/go

RUN  mkdir /go && chmod 755 /go && yum install -y git golang-bin && go get github.com/yudai/gotty && yum clean all && mkdir /workspace && chmod 777 workspace

RUN curl -sL -o /tmp/oc.tar.gz https://mirror.openshift.com/pub/openshift-v4/clients/ocp/latest/openshift-client-linux.tar.gz && \
tar -C /tmp -xf /tmp/oc.tar.gz --no-same-owner && \
mv /tmp/oc /usr/local/bin && \
chmod +x /usr/local/bin/oc && \
rm /tmp/*

RUN curl -sL -o /tmp/yq https://github.com/mikefarah/yq/releases/download/v4.25.1/yq_linux_amd64 && \
mv /tmp/yq /usr/local/bin && \
chmod +x /usr/bin/yq && \
rm /tmp/*
# For instance, VERSION=v4.25.1 and BINARY=yq_linux_amd64

RUN dnf -y install bash-completion

RUN oc completion bash >>/etc/bash_completion.d/oc_completion

RUN chmod -R 777 /tmp

WORKDIR /workspace

EXPOSE 8080

USER 1001

ENV HOME=/workspace

ENTRYPOINT ["/go/bin/gotty"]
CMD ["-w","bash"]
