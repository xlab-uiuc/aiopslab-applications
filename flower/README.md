# Flower

[Flower](https://flower.dev) is a flexible and extensible federated learning framework that simplifies the development and deployment of federated learning systems. By enabling collaboration across distributed data sources while preserving data privacy, Flower provides tools to build scalable and secure FL solutions. This integration brings the power of Flower into AIOpsLab.

The current implementation uses Docker containers to run Flower components on a local machine. The components include the `SuperLink`, `ServerApp`, `SuperNode` and `ClientApp`. 

This implementation consists of a single server and two clients, running a simple CNN model on the CIFAR-10 dataset. 

## Usage
To get started with Flower components, first move to the `flower` directory.

Run the following command to start the Flower components:
```
docker-compose up -d
```
On the first run, this will download the required Docker images. In the following runs, it will use the local images for a faster startup.

To start a federated learning task, run the following command:
```
flwr run train local-deployment --stream
```
This will start the federated learning task and stream the logs of the `ServerApp` to the console.

To stop the Flower components, run the following command:
```
docker-compose down
```

You can change various aspects of the task by modifying `train/pyproject.toml`.

## Future Work
The `kubernetes` folder consists of files to be used in the future to create a Kubernetes deployment of the Flower components.
