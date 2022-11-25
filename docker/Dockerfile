FROM ubuntu:18.04

RUN apt update && apt install -y \
    gcc-multilib \
    g++-multilib \
    gdb \
    git \
    build-essential \
    curl
RUN apt install -y python3-pip

RUN mkdir ~/.config
RUN curl https://sh.rustup.rs -sSf | sh -s -- -y
ENV PATH="/root/.cargo/bin:$PATH"
RUN (cd /root && mkdir workspace && cd /root/workspace && git clone https://github.com/helix-editor/helix && cd helix && cargo install --path helix-term && mkdir ~/.config/helix && mv runtime ~/.config/helix/runtime && rm -fr /root/workspace)
