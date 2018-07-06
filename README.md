# kafka-kompose-gcp
Kafka Kompose test docker-compose file for GCP


## Example instructions 

### Install kompose on your system
https://github.com/kubernetes/kompose/blob/master/docs/installation.md

e.g. on learn.openshift.com

sudo yum install epel-release

sudo yum -y install kompose


### Get this repo or download the docker-compose file
wget https://raw.githubusercontent.com/grahamea/kafka-kompose-gcp/master/docker-compose.yml

### Create a project
kubectl new-project rtview-dataserver-kafka

### Bring up our configuration
kompose up

### See what he have created 
kubectl get dc,svc,is,pvc,ingress

### Force a restart of rtview-dataserver-spvy updating a deployment config 
oc set env dc/rtview-dataserver-kafka RESTART=1

### Bring down (and remove) our configuration 
kompose down

### Delete the project 
oc delete project rtview-dataserver-kafka

### See the individual resources used in our configuration in openshift 
kompose convert
