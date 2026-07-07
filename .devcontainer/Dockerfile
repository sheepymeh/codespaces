FROM debian:12

ENV DEBIAN_FRONTEND=noninteractive

RUN apt-get update \
	&& apt-get install -y --no-install-recommends \
		dbus \
		firefox-esr \
		git \
		htop \
		novnc \
		procps \
		python3 \
		sudo \
		sway \
		wayvnc \
		&& apt-get clean \
	&& rm -rf /var/lib/apt/lists/*

RUN useradd -m -u 1000 -s /bin/bash vscode

RUN echo "vscode ALL=(ALL) NOPASSWD:ALL" > /etc/sudoers.d/vscode \
	&& chmod 0440 /etc/sudoers.d/vscode

COPY .devcontainer/sway /usr/local/bin/sway
RUN chmod a+x /usr/local/bin/sway

USER vscode

CMD ["/usr/local/bin/sway"]