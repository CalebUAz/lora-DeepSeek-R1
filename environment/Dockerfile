# Use an official Python image as the base
FROM python:3.12.0

# Set the working directory in the container
WORKDIR /app

# Copy all files from the current directory to the container
COPY . .

# Install system dependencies
RUN apt-get update && apt-get install -y \
    build-essential \
    && rm -rf /var/lib/apt/lists/*

# Install Python dependencies
RUN pip install --no-cache-dir \
    jupyterlab \
    transformers \
    torch \
    sentencepiece \
    unsloth \
    bitsandbytes \
    unsloth_zoo \
    wandb 
    
# Also get the latest version Unsloth!
RUN pip install --force-reinstall --no-cache-dir --no-deps git+https://github.com/unslothai/unsloth.git 

RUN sudo apt-get install python3-pip