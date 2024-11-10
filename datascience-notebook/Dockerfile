# Copyright (c) VectorMind Labs Development Team.
ARG REGISTRY=quay.io
ARG OWNER=jupyter
ARG VERSION=latest
ARG BASE_CONTAINER=$REGISTRY/$OWNER/datascience-notebook:$VERSION
FROM $BASE_CONTAINER

LABEL maintainer="Divya Antony J R <antony@vectormindlabs.com>"


# Fix: https://github.com/hadolint/hadolint/wiki/DL4006
# Fix: https://github.com/koalaman/shellcheck/wiki/SC3014
SHELL ["/bin/bash", "-o", "pipefail", "-c"]

USER root

# Some Useful Tools
RUN apt-get update --yes && \
    apt-get install --yes --no-install-recommends \
    vim curl && \
    apt-get clean && rm -rf /var/lib/apt/lists/*

# Install Azure CLI
RUN curl -sL https://aka.ms/InstallAzureCLIDeb  --output /opt/setup-scripts/setup-azure-cli.sh
RUN chmod a+x /opt/setup-scripts/setup-azure-cli.sh
RUN /opt/setup-scripts/setup-azure-cli.sh

USER ${NB_UID}

# Install All Required Extensions
# NOTE: Removed 'jupyter-collaboration' since it breaks all
# exports.
# Also no value add from the team.
RUN mamba install --yes \
    'jupyterlab-lsp' \
    'python-lsp-server[all]' \
    'r-languageserver' \
    'jupytext' \
    'texlab' \
    'pyright' && \
    mamba clean --all -f -y && \
    fix-permissions "${CONDA_DIR}" && \
    fix-permissions "/home/${NB_USER}"
