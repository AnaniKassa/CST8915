# About me 
### Full name: Anani Thierry Kassa
### Student ID: 041140713

## 1- Demo Video (CST8915-Lab7-Full-stack Cloud-native Development: Introduction to Kubernetes Basics)
- Deploying the Algonquin Pet Store application using the algonquin-pet-store-all-in-one.yaml file
- Demonstrate the RabbitMQ configuration problem.
- https://youtu.be/lHhxUmdiHWs

## 2- Written analysis of the RabbitMQ configuration issues, including:
- Whether RabbitMQ is a stateless or stateful application
    RabbitMQ is a stateful application, because it stores critical state data such as: queuedefinitions, messages in queues. This data must persist between application restarts for RabbitMQ to function correctly and reliably.

- The implications of running RabbitMQ without persistent storage
    In the provided configuration, RabbitMQ is deployed without a PersistentVolume or a PersistentVolumeClaim. This leads to significant problems: Data Loss, Non-Durable State, Service Instability, Violates message delivery guarantees.

- What happens when the RabbitMQ pod is deleted or restarted
    This may lead to different scenarios:
    - Pod is Terminated which may result in new RabbitMQ instance, all previous data gone, loss of durable queues and messages
    - Node failure which may result in no attached storage, fresh RabbitMQ instance on new node
    - Rolling update which may result in state resets, internal message state lost
    - Observable symptoms like consumers see empty queues, producers retry non-stop, services fail on reconnect

- Potential solutions to this problem (research-based)
    According to the RabbitMQ Kubernetes Deployment Best Practices, Deploy RabbitMQ clusters using StatefulSets to ensure node identity stability and persistent volume usage.

- Does using Azure Service Bus solve the issues identified with RabbitMQ Configuration in this Lab?
    YES — Azure Service Bus solves all the identified problems, since it's a fully managed, cloud-based message broker.
