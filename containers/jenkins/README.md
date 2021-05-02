## Jenkins Dockerfile
Currently only adds Terraform and Docker CLI, build and push to docker hub:

``` sh
docker build -t mwdomino/jenkins .
docker image push mwdomino/jenkins mwdomino/jenkins
```
