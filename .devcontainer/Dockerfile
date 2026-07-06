FROM mcr.microsoft.com/devcontainers/base:debian

RUN sudo apt-get update
RUN sudo DEBIAN_FRONTEND=noninteractive apt-get -y install sway wayvnc dbus novnc && sudo apt-get clean

COPY .devcontainer/sway /usr/local/bin/sway
RUN sudo chmod a+x /usr/local/bin/sway

USER 1000

CMD ["/usr/local/bin/sway"]