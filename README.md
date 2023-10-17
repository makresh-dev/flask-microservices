# Microservice Flask Application

This is a microservice application built using Flask and deployed on Kubernetes. It is designed to demonstrate how to build and deploy microservices on a Kubernetes cluster.

## Table of Contents

- [Installation](#installation)
- [Usage](#usage)
- [Contributing](#contributing)
- [License](#license)

## Installation

To install and run the application on Docker, follow these steps:

1. Before installing the application make sure you have created the custom bridge network configuration in docker by running the following command

`docker network create <name of network>`

2. Verify that the network is created or not by following command

`docker network ls`

4. Clone this repository to your local machine.
5. Navigate to the project root directory.
6. Build the python docker image by running the following command:

`docker build -t <imagefile name> .`

7. Verify that the python app image has been created successfully by running the following command:

`docker images`

8. Run the python app image in custom network by running the command:

`docker run -d -p <PORT NO.> --name <CONTAINER_NAME> --network <CUSTOM_NETWORK_NAME> <IMAGE_NAME>`

9. Run the mongodb image in custom network by running the command:

`docker run -d --name mongo --network <CUSTOM_NETWORK_NAME> mongo`

10. Verify that both containers are running on same network by running the command:

`docker inSpect <CUSTOM_NETWORK_NAME>`

## Usage

To use the microservice, you can send HTTP requests to the service's endpoint. Here's an example request:

`curl http://<service-ip>:<service-port>/tasks`


This should return a JSON response with a greeting message.

## Contributing

If you'd like to contribute to this project, please fork the repository and create a new branch. Pull requests are welcome!

## License

This project is licensed under the MIT License - see the [LICENSE.md]