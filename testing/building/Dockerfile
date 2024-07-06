# Use an official base image
FROM ubuntu:20.04

# Update and install any necessary packages
RUN apt-get update && apt-get install -y \
    curl \
    vim \
    && rm -rf /var/lib/apt/lists/*

# Set a command that will run indefinitely
CMD ["sh", "-c", "while true; do echo Hello World; sleep 60; done"]
