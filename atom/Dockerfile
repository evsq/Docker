# Usage
# docker build . -t atom
# docker run -v /tmp/.X11-unix/:/tmp/.X11-unix/ -v ${HOME}/.atom:/home/atom/.atom -e DISPLAY atom

FROM ubuntu:latest

RUN apt-get update && apt-get install -y --no-install-recommends \
    apt-transport-https \
    ca-certificates \
    gnupg \
    wget 

# Add the atom ubuntu/debian package repo
RUN wget -qO - https://packagecloud.io/AtomEditor/atom/gpgkey | apt-key add -
RUN sh -c 'echo "deb [arch=amd64] https://packagecloud.io/AtomEditor/atom/any/ any main" > /etc/apt/sources.list.d/atom.list'

# Install dependencies
RUN apt-get update && apt-get install -y --no-install-recommends \
    atom \
    gconf2 \
    gconf-service \
    git \
    gvfs-bin \
    libasound2 \
    libcap2 \
    libgconf-2-4 \
    libgtk2.0-0 \
    libnotify4 \
    libnss3 \
    libxkbfile1 \
    libxss1 \
    libxtst6 \
    libx11-xcb-dev \
    xdg-utils && \
    rm -rf /var/lib/apt/lists/*

ENTRYPOINT ["atom","-f"]
