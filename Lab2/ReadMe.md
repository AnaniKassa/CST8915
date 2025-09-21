# 1. Youtube Link
https://youtu.be/R2EX0p0PgvQ

# 2. What changes did you make to the order-service and product-service to comply with the Configurations and Backing Services factors of the 12-Factor App methodology?
- To comply with configuration for the order-service, I changed the index.js file content which no longer contain the static RabbitMQ connection string but an environment variable (const RABBITMQ_CONNECTION_STRING = process.env.RABBITMQ_CONNECTION_STRING ) and the port (const PORT = process.env.PORT) to establish a dynamic connection to RabbitMQ.

- On the other hand, the main.rs file has been modified for the product-service by inserting the dotenv create to load environment variables from a .env file during he development only.

- In terms of backing services factors that has been changed among the 12-Factor, **Codebase**, **Dependencies**, **Config**, and **Backing services** are the factors used to change both the order-service and the product-service.



# 3. Why is it important to use environment variables instead of hard-coding configurations in your application?
The environment variables were used to ensure that the order-service connects to the external RabbitMQ instance, as it's running on a different VM as compared to the other services.


# 4. Why is it important to have separate repositories for each microservice? How does this help maintain independence and scalability of each service?
Having a seperate repositories for each microservices is to break down the monolithic way of having all services together. This shows that each services can be created and developed independentely. In terms of independency and scalability, these services can be developed seperately from each other and any change that might appear after deployment of those service will be apply to the concerned service without affecting the others.

# 5. Links to the three service repositories you created
   - order-service: https://github.com/AnaniKassa/order-service.git
   - product-service : https://github.com/AnaniKassa/product-service.git
   - store-front: https://github.com/AnaniKassa/store-front.git

# 6. Lessons learned
   - After creating the VM seperately for RabbitMQ and the other services, I was was wondering how can these 2 VM communicate to each other, and I reacalled that this can be done by creating a **network peering** between them.
   - Following the instructions as labelled, this lead to a bit of confusion. After completing this lab, here is the logic I think of: 
        1. create the repo for each services
        2. create one VM for RabbitMQ and another for the others services 
        3. connect to the VM using VSCode and clone each repo in the second VM. 
        4. perform the configuration on each services 
        5. run each service and make sure they are all up together 
        6. proceed to the test on the store-front and the RabbitMQ backend service.