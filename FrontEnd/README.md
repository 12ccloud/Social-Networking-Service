# Social-Networking-Service
A geo-based social network web application, support to search nearby posts and filter the posts with face filtering technique。

* Frond-End: Implemented by React.js. Created a token based register/login/logout flow. 
* Back-End:Implemented by Golang. 
  - Set up cloud project on Google Compute Engine(GCE) instance.(VM instance)
  - Utilized Elasticsearch. (used as DataBase, also deployed to GCE)
  - JSON Web Token(JWT) for authentication

* Other Tech Tools: GeoLocation API, Google Vision API, Google Map API, , Google Cloud Storage (GCS), Ant Design,
* Deployed option:
  - Google Cloud (Google Kubernetes Engine GKE) - enhance scaling and reliability, make the serivce run in a cluster with multiple virtual machines. A sinlge
  failure of one virual machine will not affect the whole service.
