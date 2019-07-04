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
docker run -v <PATH-TO-YOUR-CREDENTIALS-ON-HOST_MACHINE>/.aws:/root/.aws -v <PATH-TO-YOUR-SERVERLESS-PROJECT>:/root/classify-lambda -v /var/run/docker.sock:/var/run/docker.sock b3219d2aa42b
```
