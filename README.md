# Dockerfile Build Error: No such file or directory

This repository demonstrates a common error when building Docker images: the `COPY` instruction failing because a required file is missing or in the wrong location. 

The original `Dockerfile` attempts to install Python packages from a `requirements.txt` file. However, the `COPY` command copying the `requirements.txt` file is placed before the actual file creation, leading to the failure.

The solution demonstrates the correct order of `COPY` instructions, ensuring the `requirements.txt` file exists before attempting to install packages.

## Steps to Reproduce
1. Clone this repository.
2. Attempt to build the image using the original `Dockerfile` using command: `docker build -t my-app .`
3. Observe the error. 
4. Modify Dockerfile with the solution code
5. Build image again to verify the solution