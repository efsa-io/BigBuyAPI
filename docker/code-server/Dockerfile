ARG CODE_SERVER_IMAGE=codercom/code-server:3.8.0

FROM $CODE_SERVER_IMAGE

USER root

USER coder

WORKDIR /home/coder

RUN \
    /usr/bin/entrypoint.sh --install-extension 42Crunch.vscode-openapi && \
    /usr/bin/entrypoint.sh --install-extension ChrisRu.vscode-nightsky && \
    /usr/bin/entrypoint.sh --install-extension codezombiech.gitignore && \
    /usr/bin/entrypoint.sh --install-extension redhat.vscode-xml && \
    /usr/bin/entrypoint.sh --install-extension redhat.vscode-yaml && \
    /usr/bin/entrypoint.sh --install-extension mermade.openapi-lint && \
    /usr/bin/entrypoint.sh --install-extension arjun.swagger-viewer && \
    /usr/bin/entrypoint.sh --install-extension tomoki1207.pdf
    

ENTRYPOINT ["/usr/bin/entrypoint.sh", "--auth", "none", "--disable-telemetry", "--disable-update-check", "--bind-addr", "0.0.0.0:8080", "--verbose", "."]
