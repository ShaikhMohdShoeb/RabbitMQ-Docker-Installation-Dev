RabbitMQ Docker Installation
This repository contains scripts and files to automate the installation of RabbitMQ in a Docker container using Ubuntu/Debian.

- Prerequisites: 
  Docker, Ubuntu 20.04

 -INSTALLATION STEPS

- Clone this repository to your local machine.

  $ git clone https://github.com/your_username/rabbitmq-docker.git

- Change directory to the cloned repository.

  $ cd rabbitmq-docker

- Run the build-rbtmq-docker.sh script to build the Docker image.

  $ ./build-rbtmq-docker.sh

- Start the RabbitMQ container.

  $ docker run -d -p 5672:5672 rabbitmq-docker

Verify that RabbitMQ is running by visiting the RabbitMQ management console at http://<ip>:15672. The default username and password are "guest".

- Contents

Dockerfile: A Dockerfile is a script that contains a collection of commands and instructions that will be automatically executed in sequence to create a Docker image. This Dockerfile installs RabbitMQ in a Docker container using Ubuntu 20.04 as a base image, and also installs necessary packages such as sudo, python3, python3-pip, htop, less, zip, gzip, and pika Python package.

cloudsmith.sh: This is a script that installs the RabbitMQ package and its dependencies from the Cloudsmith repository. This script is called by the build-rbtmq-docker.sh script.

build-rbtmq-docker.sh: This script builds the RabbitMQ Docker image using the Dockerfile and cloudsmith.sh script with --no-cache option. This script is responsible for creating the Docker image that will run RabbitMQ.

producer.py: This is a Python script from the official RabbitMQ tutorial that sends messages to RabbitMQ. It uses the pika package to connect to RabbitMQ and send messages.

consumer.py: This is a Python script from the official RabbitMQ tutorial that receives messages from RabbitMQ. It uses the pika package to connect to RabbitMQ and receive messages.


- Usage

Modify the tutorial-one-python/producer.py and tutorial-one-python/consumer.py files to send and receive messages specific to your use case.


