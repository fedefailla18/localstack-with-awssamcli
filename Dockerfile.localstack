# Use the official LocalStack image as the base image
FROM localstack/localstack:latest

RUN pip install aws-sam-cli-local

# Set Brew binary path in the environment
ENV PATH=~/.linuxbrew/bin:~/.linuxbrew/sbin:$PATH

# Add the Brew binary path to ~/.bashrc
RUN echo 'export PATH=~/.linuxbrew/bin:~/.linuxbrew/sbin:$PATH' >> ~/.bashrc
