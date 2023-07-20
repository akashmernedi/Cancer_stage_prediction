# Predicting cancer stages using machine learning on Amazon ECS

## Problem Statement

Machine learning plays a crucial role in various industries, and a cancer prediction system allows doctors to input medical records through a web interface and obtain predictions about the cancer stage. To make the model accessible to users, developers can deploy it using web applications and receive real-time predictions. Cloud deployment offers several advantages, including the ability to autoscale to handle high traffic and access to more computational power for faster outputs. This cloud deployment approach is cost-effective as developers don't need to invest in expensive hardware and resources for running the model.

## Design of Proposed Solution

![image](https://github.com/akashmernedi/Cancer_stage_prediction/assets/92681996/0a5416ad-8537-4ac4-a6e0-ce0f0322e106)

## Implementation of Solution

1. Web application to deploy ML model using Python and Flask
1. Containerization of web application using Docker
1. Deployment to the cloud using AWS

![image](https://github.com/akashmernedi/Cancer_stage_prediction/assets/92681996/de762d1f-3818-4c0d-9aaa-9ddf69f381d2)

## Requirements 

1. Breast Cancer Wisconsin dataset to train the model.
2. Python packages like Numpy, Panda, etc. to preprocess the dataset.
3. Flask web server.
4. Docker to deploy the web server to the cloud.
5. Amazon ECR to register the docker images.
6. Amazon ECS instance to host the application.
7. CloudWatch metrics for monitoring

## Deployment of Solution

1. Create an ML model  after preprocessing the dataset and locally run the flask server.
2. Create a policy in which all permissions for the Elastic Container Registry (ECR) are mentioned and attach full access to Amazon ECS. 
3. Create a private flask server for the Elastic Container Registry repository and use the Windows push command to push the Docker image.
4. Select the cluster template and create a cluster in Amazon ECS. Then check the status of the created cluster and configure the tasks and container definitions.
5. Configure the security groups to allow the port and add the container definitions.
6. View the status of the cluster created and wait for the task status to change to running.
7. The IP address for the running task is checked and then the IP address of the running task can be opened to see the ML model deployed on the cloud.

## Testing and Validation

1. Cross-checked the network traffic locally to confirm whether all the parameters passing to the machine learning model are getting the values as input or not.

![image](https://github.com/akashmernedi/Cancer_stage_prediction/assets/92681996/6af4a6af-1e6d-4594-8a8e-20a2f157bd74)

2. Jaccard score index of the model to measure the validity of the ML model
   
![image](https://github.com/akashmernedi/Cancer_stage_prediction/assets/92681996/37c4a7c2-3f2b-4904-a059-af82a79fe19f)

## Experimental Results 

1. Entered cancer patient records and checked the results predicted by the ML model.

![image](https://github.com/akashmernedi/Cancer_stage_prediction/assets/92681996/4afddc50-849c-4dd4-99ef-92e8389e7fcb)
![image](https://github.com/akashmernedi/Cancer_stage_prediction/assets/92681996/a62c5554-c15b-4a81-811a-69066e496b23)

2. Inspected metrics using CloudWatch

![image](https://github.com/akashmernedi/Cancer_stage_prediction/assets/92681996/b332f133-8c12-4759-92a1-e1dfd8e7514f)


