Bootstrap: docker
From: ubuntu:22.04

%post
    apt-get update
    apt-get install -y --no-install-recommends \
        ca-certificates \
        curl \
        git \
        python3 \
        python3-pip
    rm -rf /var/lib/apt/lists/*

%environment
    export LC_ALL=C.UTF-8
    export LANG=C.UTF-8

%runscript
    exec /bin/bash "$@"
