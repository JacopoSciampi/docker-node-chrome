FROM node:18
LABEL maintainer="Jacopo Sciampi <github.com/JacopoSciampi>"

SHELL ["/bin/bash", "-o", "pipefail", "-c"]

RUN apt-get update -qq \
  && apt-get install -qq --no-install-recommends \
    wget \
    curl \
    ca-certificates \
    libx11-xcb1 \
    libxcomposite1 \
    libxrandr2 \
    libglu1-mesa \
    libnss3 \
    libatk-bridge2.0-0 \
    libatk1.0-0 \
    libatspi2.0-0 \
    libcups2 \
    libdbus-1-3 \
    libdrm2 \
    libgbm1 \
    libgtk-3-0 \
    libu2f-udev \
    libvulkan1 \
    libxdamage1 \
    libxfixes3 \
    fonts-liberation \
    libxkbcommon0 \
    xdg-utils \
    libasound2 \
  && apt-get clean \
  && rm -rf /var/lib/apt/lists/*
RUN wget https://mirror.cs.uchicago.edu/google-chrome/pool/main/g/google-chrome-stable/google-chrome-stable_118.0.5993.117-1_amd64.deb \
  && dpkg -i google-chrome-stable_118.0.5993.117-1_amd64.deb \
  && apt-get -f install -y \
  && rm google-chrome-stable_118.0.5993.117-1_amd64.deb

RUN ln -sf /opt/google/chrome/google-chrome /usr/bin/google-chrome