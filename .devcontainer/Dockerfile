FROM node:18

# Install basic development tools
RUN apt update && apt install -y less man-db sudo

# Ensure default `node` user has access to `sudo`
ARG USERNAME=node
RUN echo $USERNAME ALL=\(root\) NOPASSWD:ALL > /etc/sudoers.d/$USERNAME \
    && chmod 0440 /etc/sudoers.d/$USERNAME

# Set `DEVCONTAINER` environment variable to help with orientation
ENV DEVCONTAINER=true

# Install PNPM
RUN curl -fsSL https://get.pnpm.io/install.sh | sh -

# Set PNPM global bin path to the PATH environment variable
ENV PNPM_HOME=/usr/local/pnpm-global
ENV PATH="$PNPM_HOME/bin:$PATH"
