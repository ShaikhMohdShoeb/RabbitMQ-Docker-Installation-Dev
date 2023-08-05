# RabbitMQ Docker Installation
This repository contains scripts and files to automate the installation of RabbitMQ in a Docker container using Ubuntu/Debian.

## Prerequisites
Before proceeding with the installation, ensure you have the following prerequisites:
- Docker
- Ubuntu 20.04

## Installation Steps
Follow the steps below to install RabbitMQ in a Docker container:
- Clone this repository to your local machine.
````
git clone https://github.com/ShaikhMohdShoeb/RabbitMQ-Docker-Installation-Dev.git
````

- Change directory to the cloned repository.
````
cd rabbitmq-docker
````

- Run the build-rbtmq-docker.sh script to build the Docker image.
````
./build-rbtmq-docker.sh
````

- Start the RabbitMQ container
````
docker run -d -p 5672:5672 rabbitmq-docker
````

- Verify that RabbitMQ is running by visiting the RabbitMQ management console at http://:15672. The default username and password are "guest".

## This repository contains the following files:
**Dockerfile:** A Dockerfile that installs RabbitMQ in a Docker container using Ubuntu 20.04 as a base image. It also installs necessary packages such as sudo, python3, python3-pip, htop, less, zip, gzip, and pika Python package.

**cloudsmith.sh:** This script installs the RabbitMQ package and its dependencies from the Cloudsmith repository. It is called by the build-rbtmq-docker.sh script.
build-rbtmq-docker.sh: This script builds the RabbitMQ Docker image using the Dockerfile and cloudsmith.sh script with the --no-cache option. It is responsible for creating the Docker image that will run RabbitMQ.

**build-rbtmq-docker.sh:** This script builds the RabbitMQ Docker image using the Dockerfile and cloudsmith.sh script with --no-cache option. This script is responsible for creating the Docker image that will run RabbitMQ.

**producer.py:** A Python script from the official RabbitMQ tutorial that sends messages to RabbitMQ. It uses the pika package to connect to RabbitMQ and send messages.

**consumer.py:** A Python script from the official RabbitMQ tutorial that receives messages from RabbitMQ. It uses the pika package to connect to RabbitMQ and receive messages.

## Usage
Modify the producer.py and consumer.py files in the Producer_consumer_API's directory to send and receive messages specific to your use case.



