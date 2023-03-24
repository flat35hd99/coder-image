FROM codercom/code-server:ubuntu

USER root

# Add trusted SSH key fingerprints
COPY --chown=coder:coder ./known_hosts /home/coder/.ssh/known_hosts
RUN mkdir -p /home/coder/.local/bin/ \
    && ln -s /usr/bin/python3 /home/coder/.local/bin/python
    && chown coder:coder \
        /home/coder/.local \
        /home/coder/.local/bin/ \
        /home/coder/.local/bin/python

ENV DEBIAN_FRONTEND=noninteractive
ENV PATH="$PATH:/home/coder/.local/bin"
RUN apt-get update -y -qq \
    && echo ttf-mscorefonts-installer msttcorefonts/accepted-mscorefonts-eula select true | sudo debconf-set-selections \
    && apt-get install -y -qq \
        wget \
    && apt-get clean

USER 1000
ENV USER=coder
WORKDIR /home/coder
