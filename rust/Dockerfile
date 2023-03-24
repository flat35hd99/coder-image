FROM codercom/code-server:ubuntu

# Add trusted SSH key fingerprints
COPY --chown=coder:coder ./known_hosts /home/coder/.ssh/known_hosts

RUN curl https://sh.rustup.rs -sSf | sh -s -- -q -y
