## About me 
### Full name: Anani Thierry Kassa
### Student ID: 041140713

# Lab 8 - CST8915 Full-stack Cloud-native Development: Deploying and Managing the Algonquin Pet Store (On Steroids)

## Submission

This submission repository include:

### 1. A README.md file with:

- The YouTube demo video link
https://youtu.be/0NvtTXPgEis

### 2. Written explanation of your solution to Task 2

- To demonstrate persistence, I inserted a document into MongoDB, deleted the MongoDB pod, and confirmed that the data remained after the pod was recreated. This shows that Kubernetes successfully reused the PersistentVolumeClaim (PVC) and maintained data storage independently of pod lifecycle.

- To validate persistence, I created a durable queue and published a persistent message in RabbitMQ. After deleting the RabbitMQ pod, I verified that the queue and message were still present when the pod was recreated. This demonstrates that the RabbitMQ StatefulSet successfully uses its PVC to persist data across pod restarts.

- Both MongoDB and RabbitMQ StatefulSets were tested for persistence by inserting test data, deleting the pods, and confirming that the data still existed after the pods were recreated. This demonstrates that Kubernetes correctly binds PersistentVolumeClaims (PVCs) to the StatefulSets and that the data persists independently of pod lifecycle. MongoDB replica set members maintained oplogs and documents, while RabbitMQ retained durable queues and persistent messages, proving that storage volumes were functioning as expected.

### 3. Updates files
- Your updated aps-all-in-one-Task1.yaml file used for Task 1

- Your updated aps-all-in-one-Task2.yaml file used for Task 2