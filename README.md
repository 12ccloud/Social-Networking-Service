# Social-Networking-Service
A geo-based social network web application, support to search nearby posts and filter the posts with face filtering technique。

* Frond-End: Implemented by React.js. Created a token based register/login/logout flow. <br>
Design home page includes register and login by using React Router.<br>
Link to a react router setup demo to my other repo: (https://github.com/12ccloud/React-Router-setup-demo)
* Back-End:Implemented by Golang. 
  - Set up cloud project on Google Compute Engine(GCE) instance.(VM instance)
  - Utilized Elasticsearch. (used as DataBase, also deployed to GCE)
  - JSON Web Token(JWT) for authentication

* Other Tech Tools: GeoLocation API, Google Vision API, Google Map API,  Google Cloud Storage (GCS), Ant Design
* Deployed option:
  - Google Cloud (Google Kubernetes Engine GKE) - enhance scaling and reliability, make the serivce run in a cluster with multiple virtual machines. A sinlge
  failure of one virual machine will not affect the whole service.
  
## About Tech Stacks
**1. Elasticsearch**<br>
* Install Elasticsearch (open source) on GCE VM instance, and connect project with Elasticsearch
* Since this social networking service is designed as geo-based, the Elasticsearch has good performance on range search to help this program to store users' data and enhace the speed of querying data.
* Elasticsearch has been implmented by k-d tree and is able to search in a k dimensional space.


**2. Google Cloud Storage (GCS)**<br>
* The Google Cloud Storage (GCS) was used to store users' media file.
* The database is not convenient for storing binary file, and binary file will increase the size of database.
* Store the media file in GCS, then store the corresponding link (metadata) in database (Elasticsearch in this program).

**3. Google Kubernetes Engine (GKE)**<br>
* Build the program into a docker image, push the image to virtul machines which are managed by Google Kubernetes Engine.
* Example code to push the local Docker image to a remote registry (Dockerhub is used in this example:  https://hub.docker.com/)
```
sudo docker push <yourDockerHubAccountId>/<yourProgramName>
```
* Set the load-balancer to distribute the incoming queries and balance the load of user traffic.

