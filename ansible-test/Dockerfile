FROM debian:bookworm

ENV DEBIAN_FRONTEND=noninteractive

RUN apt-get update && \
    apt-get install -y \
        ansible \
        git \
        ssh \
        sudo \
        curl \
        python3 \
        python3-pip \
        passwd \
	python3-venv \
    && apt-get clean

RUN python3 -m venv /opt/venv
ENV PATH="/opt/venv/bin:$PATH"
RUN pip3 install mitogen

RUN echo "root:root" | chpasswd

WORKDIR /root

CMD [ "/bin/bash" ]
