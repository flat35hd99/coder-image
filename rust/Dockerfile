FROM codercom/code-server:ubuntu

# Add trusted SSH key fingerprints
COPY --chown=coder:coder ./known_hosts /home/coder/.ssh/known_hosts

RUN curl https://sh.rustup.rs -sSf | sh -s -- -q -y

USER root
ENV DEBIAN_FRONTEND=noninteractive
ENV PATH="$PATH:/home/coder/.local/bin"
RUN apt-get update -y -qq \
    && apt-get install -y -qq \
        wget \
        gcc \
    && apt-get clean

USER 1000
ENV USER=coder
WORKDIR /home/coder
