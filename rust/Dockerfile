FROM codercom/code-server:ubuntu

# Add trusted SSH key fingerprints
COPY --chown=coder:coder ./known_hosts /home/coder/.ssh/known_hosts

RUN curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh -- -q -y
