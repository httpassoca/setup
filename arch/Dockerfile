# Use the latest Arch Linux base image
FROM manjarolinux/base

# Update the system and install necessary packages
RUN pacman -Syu --noconfirm && \
    pacman -S nano ansible sudo git which --noconfirm  # Added sudo here

# Create a new user 'passoca' with home directory and no login shell
# Replace 'passoca' with your preferred username if necessary
RUN useradd -m -d /home/passoca -s /bin/bash passoca && \
    echo "passoca ALL=(ALL) NOPASSWD: ALL" > /etc/sudoers.d/passoca  # Allow 'passoca' to use sudo without a password

# Set the working directory to /app
WORKDIR /home/passoca

# Copy local files into the container
COPY . .

# Change ownership of the /app directory to 'passoca'
RUN chown -R passoca:passoca /home/passoca

# Switch to the new user 'passoca'
USER passoca

# Install the required Ansible collection for community general modules
RUN ansible-galaxy collection install community.general

# Set the default command to run when starting the container
CMD ["bash"]

