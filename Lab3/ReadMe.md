# About me 
### Full name: Anani Thierry Kassa
### Student ID: 041140713

# 1- Demo Video (Max 5 minutes)
https://youtu.be/Naz1KDe1dfc

- Disclaimer!!!
    - Sorry, I faced a deployment issue while recording but fixed it. This has extended the video's length to 10 minutes.

# 2- Reflection Questions

- What challenges did you encounter when configuring environment variables in the GitHub Actions workflow?
    - The challenge was at first, I was just copying and paste https://order-service-app.azurewebsites.net/ and replaced "order-service-app" by "order-service-appone" (my own). Still the front-store wasn't able to load the product service. Later on, I found out that, I have to copy the URL from the Azure portal under each Azure Web App services - "order-service-app" and "product-service-app".

- How does deploying microservices on Azure Web App Service differ from running them locally?
    - It is a pretty straight forward process, with just few click of configuration in the Azure portal, you are able to deploy your backend services, all you need is to have each microservice github repo ready. On the other hand, there is lot of environment setup to go through when deploying them locally.

- Why is it important to use environment variables for configurations in a cloud environment?
    - It is important to let the microservices communicate through out the port that you allow in the environment variable. That is where you tell the backend service to send their traffic over RabbitMQ using the RABBITMQ-CONNECTION-STRING.

# 3- Links to the three service repositories you created in lab 2:
- order-service: https://github.com/AnaniKassa/order-service.git
- product-service: https://github.com/AnaniKassa/product-service.git
- store-front: https://github.com/AnaniKassa/store-front.git

# 4- Notes about setup challenges or lessons learned.
   The following are my steps to successfully complete the lab
   - Refactor the product-service in python 
   - Create RabbitMQ VM and make it ready
   - Create the two backend service in the Azure portal, for each service refactor them properly according to the 12-factors. For order-service make sure of using a Node-version ~ 20 LTS and for the product-service use the port 3030 in your python file.
   - While creating the Azure static web app, here the store-front, make sure the env varible in your github workflow file are copied from Azure Webb App in Azure portal.
   - Make sure every service is up and runing
   - Enjoy!