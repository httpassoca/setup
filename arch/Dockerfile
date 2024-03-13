# Use the latest Arch Linux base image
FROM menci/archlinuxarm:latest

# Update the system
RUN pacman -Syu --noconfirm

# Install a basic text editor and any other packages you need
RUN pacman -S nano --noconfirm

# Set the working directory to /app
WORKDIR /app

# Copy local files into the container
COPY . .

# Set the default command to run when starting the container
CMD ["bash"]
