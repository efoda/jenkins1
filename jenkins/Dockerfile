FROM engyfouda/jenkinsci:blueocean

USER root 

COPY ["entrypoint.sh", "/"]

RUN apt-get update && \
    apt-get install sudo && \
    chmod 755 /entrypoint.sh
RUN apt-get update \
      && apt-get upgrade -y \
      && apt-get install -y sudo libltdl-dev \
      && rm -rf /var/lib/apt/lists/*
RUN echo "jenkins ALL=NOPASSWD: ALL" >> /etc/sudoers

ENTRYPOINT ["/bin/bash","-c","./entrypoint.sh"]
