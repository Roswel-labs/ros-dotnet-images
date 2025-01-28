# Base image from sloretz for ROS 2 Jazzy
FROM ghcr.io/sloretz/ros:jazzy-ros-core

# Install prerequisites
RUN apt-get update && \
    apt-get install -y wget apt-transport-https && \
    rm -rf /var/lib/apt/lists/*

# Add Microsoft package signing key and repository
RUN wget https://packages.microsoft.com/config/ubuntu/24.04/packages-microsoft-prod.deb -O packages-microsoft-prod.deb && \
    dpkg -i packages-microsoft-prod.deb && \
    rm packages-microsoft-prod.deb

# Install ASP.NET Core Runtime
RUN apt-get update && \
    apt-get install -y aspnetcore-runtime-8.0 && \
    rm -rf /var/lib/apt/lists/*

# Define LD_LIBRARY_PATH before using it
ENV LD_LIBRARY_PATH=/usr/local/lib

# Now modify or append to LD_LIBRARY_PATH
ENV LD_LIBRARY_PATH=/some/path:$LD_LIBRARY_PATH

# Set the default command
CMD ["bash"]
