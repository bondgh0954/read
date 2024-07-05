
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

 create mod-dpl.yaml file using the visual studio code editor
 
   mod-dpl.yaml <br/>
     check docker hub for official installation guide of mongodb image <br/>
     create a secret key in minikube
     
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
