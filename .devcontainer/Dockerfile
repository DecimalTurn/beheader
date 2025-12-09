# Use Alpine Linux for smaller image size
FROM alpine:3.19

# Install system dependencies in a single layer
RUN apk add --no-cache \
    bash \
    curl \
    unzip \
    zip \
    ffmpeg \
    imagemagick \
    python3 \
    ca-certificates \
    git \
    gcompat \
    libstdc++ \
    shadow

# Install Bun - system-wide installation
RUN curl -fsSL https://bun.sh/install | bash && \
    mv /root/.bun /usr/local/bun && \
    ln -s /usr/local/bun/bin/bun /usr/local/bin/bun

# Install Bento4 (mp4edit)
RUN curl -L https://www.bok.net/Bento4/binaries/Bento4-SDK-1-6-0-641.x86_64-unknown-linux.zip -o /tmp/bento4.zip && \
    unzip /tmp/bento4.zip -d /opt && \
    mv /opt/Bento4-SDK-* /opt/bento4 && \
    rm /tmp/bento4.zip
ENV PATH="/opt/bento4/bin:${PATH}"
