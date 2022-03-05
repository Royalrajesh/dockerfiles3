FROM buildkite/agent:3

RUN curl -fsSL "https://github.com/GoogleCloudPlatform/docker-credential-gcr/releases/download/v2.1.0/docker-credential-gcr_linux_amd64-2.1.0.tar.gz" \
    | tar xz --to-stdout docker-credential-gcr \
    > /usr/local/bin/docker-credential-gcr && chmod +x /usr/local/bin/docker-credential-gcr

RUN docker-credential-gcr configure-docker

RUN curl -fsSL "https://download.docker.com/linux/static/stable/x86_64/docker-20.10.9.tgz" | tar xz

RUN curl -LO "https://dl.k8s.io/release/$(curl -L -s https://dl.k8s.io/release/stable.txt)/bin/linux/amd64/kubectl"
RUN install -o root -g root -m 0755 kubectl /usr/local/bin/kubectl

RUN cp docker/docker /usr/local/bin/docker
