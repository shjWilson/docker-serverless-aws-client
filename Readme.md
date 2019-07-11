# Environment to build and deploy lambda function 

Use this project ot build docker image providing building/deployment
environment for aws lambda function wrapping TensorFlow models.

## Getting Started

Just run docker build to build an image.

### Running docker

Assuming that you have set up aws client credentials just mount .aws folder
from the host system to the /root/.aws folder in docker container. That
way you don't have to configure it every single time when you run docker
container.

Following example show how to run dokcer image with mounting folders 

```
docker run -v <PATH-TO-YOUR-CREDENTIALS-ON-HOST_MACHINE>/.aws:/root/.aws -v <PATH-TO-YOUR-SERVERLESS-PROJECT>:/root/classify-lambda -v /var/run/docker.sock:/var/run/docker.sock <IMAGE ID>
```

Where:

1. To get IMAGE-ID run command 
   
   ```docker image ls```
   
   You should see line 
   
   ```serverless latest 0f5875eda9b2 6 days ago 2.55GB```
   
   - aws-serverless-client - is a tag name
   - latest - is version name
   - 0f5875eda9b2 - is the image id
   
If you don't have `aws-serverless-client` image build it.
To build the image just check out this project, get in to directory and run
follwoing command: 

```docker build . -t aws-serverless-client```  
   