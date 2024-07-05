
<h1>Demo Project</h1>

<h2>Project Description</h2>
Setup local K8s cluster with minkube
Deploy MongoDB and MongoExpress with configuration and credentials extrated into configMap and Sercret
<br />


<h2>Technologies used</h2>

- <b>Kubernetes</b> 
- <b>Docker</b>
- <b>MongoDB</b>
- <b>Mongo Express</b>

<h2>Detailed Description of Project </h2>

<p align="center">
Install minikube and start minikube with docker as the driver: <br/>
<img src='./src/image1.png' height="80%" width="80%" alt="Disk Sanitization Steps">


<br />
<br />
Create yaml configuration files to start mongodb  deployment and service:<br/>
1. Create a mongodb pod/deployment and in order to communicate with the pod, a Service is required <br/>
 create internal service to allow only internal components in the cluster to communicate with each other <br/>
 create ("mod-dpl.yaml") file using the visual studio code editor <br/>
 

     check docker hub for official configuration guide of mongodb image 
     two environmental variables that need to be set are 
     MONGO_INITDB_ROOT_USERNAME:
     MONGO_INITDB_ROOT_PASSWORD:
     NB: Because the configuration file is going to be checked into the repository, it is not a 
     good practice to add username and password in the configuration file 
     therefore: 
     create a secret key in minikube 
     create a new file "mod-secret.yaml" 
     the kind:"Secret" 
     use base64 to generate the key value pair 
     echo -u "username"|base64
     echo -u "password"|base64
create the secret and mogodb deployment using "Kubectl apply command"
<img src='./src/image2.png' height="80%" width="80%" alt="Disk Sanitization Steps">

Create a mongodb Service in same mongodb deployment configuration file
NB: The "target port in the service should be the same as the deployment port
create the mongodb service using 'kubectl apply command'
<img src='./src/image3.png' height="80%" width="80%" alt="Disk Sanitization Steps">

Create mongo express deployment("moe-depl.yaml") and service 
check docker hub for official configuration guide of mongodb image 
three environmental variables that need to be set are 
ME_CONFIG_MONGODB_ADMINUSERNAME            
ME_CONFIG_MONGODB_ADMINPASSWORD
ME_CONFIG_MONGODB_SERVER
The admin username and password is also reference from the secret key created earlier
Create a configMap ("moe-configmap")to reference the server
the name of the mod-deployment server should be used as the value
<img src='./src/image4.png' height="80%" width="80%" alt="Disk Sanitization Steps">



create a new file "moe-deployment.yaml"


 
   
     
<img src="https://i.imgur.com/tcTyMUE.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Enter the number of passes: <br/>
<img src="https://i.imgur.com/nCIbXbg.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Confirm your selection:  <br/>
<img src="https://i.imgur.com/cdFHBiU.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Wait for process to complete (may take some time):  <br/>
<img src="https://i.imgur.com/JL945Ga.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Sanitization complete:  <br/>
<img src="https://i.imgur.com/K71yaM2.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Observe the wiped disk:  <br/>
<img src="https://i.imgur.com/AeZkvFQ.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
