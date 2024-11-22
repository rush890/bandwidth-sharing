FROM ubuntu:24.04

RUN <<EOF
    apt update
    apt install --yes wget lsb-release
    touch /usr/bin/hostnamectl && chmod a+x /usr/bin/hostnamectl # fake hostnamectl
    touch /usr/bin/systemctl && chmod a+x /usr/bin/systemctl     # fake systemctl

    mkdir -p /etc/earnapp/

    apt clean
    apt autoremove --yes
    rm -rf /**var**/lib/apt/lists/*
EOF

CMD echo "Starting earnapp.." && \
    echo -n "${EARNAPP_ID}" > /etc/earnapp/uuid && \
    wget -qO- https://brightdata.com/static/earnapp/install.sh | bash -s -- -y && \
    earnapp run
