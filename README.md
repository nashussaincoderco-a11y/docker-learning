# Docker Learning



<img width="524" height="47" alt="image" src="https://github.com/user-attachments/assets/a407826b-9e8d-488e-a3f0-b3509ce049cf" />




<img width="821" height="435" alt="image" src="https://github.com/user-attachments/assets/02646cd2-a796-44a1-9cbf-2703ed957643" />






<img width="1110" height="414" alt="image" src="https://github.com/user-attachments/assets/65a12dcb-3765-4700-a447-41cc2408ab0e" />






<img width="754" height="418" alt="image" src="https://github.com/user-attachments/assets/86089996-4b9a-46be-97e5-48a6325eadea" />






## Containerise Web Application






<img width="1472" height="501" alt="image" src="https://github.com/user-attachments/assets/34a03b99-2af4-4d1f-ad30-4fc85afec963" />






<img width="1119" height="264" alt="image" src="https://github.com/user-attachments/assets/1899c541-72a1-41f6-86ae-313daee14b38" />






<img width="1577" height="1044" alt="image" src="https://github.com/user-attachments/assets/2f9398b6-bb1b-48e7-a9ae-c12c52383de5" /> 




docker build -t hello-flask (This initiates the build process, -t flag tags the image with a name where we are nakming "hello-flash") 






<img width="1269" height="223" alt="image" src="https://github.com/user-attachments/assets/dddd8ae1-d230-4f7f-9411-00a3e388680f" />






docker run -d -p 5002:5002 hello-flask - (the -d flag runs the container in detached mode which means running it in the background), -p 5002:5002 is basically mapping 5002 on current machine to 5002 in the container. The name of the image we are using is hello-flask. 






## Docker Networking 







docker run -d --name mydb --network  my-custom-network -e MYSQL_ROOT_PASSWORD=my-secret-pw mysql:8
bash: /usr/bin/docker: No such file or directory





docker build -t hello-flask-mysql . 







<img width="834" height="49" alt="image" src="https://github.com/user-attachments/assets/856e92b5-41a2-472c-b2ef-213bc886beb0" />











<img width="468" height="250" alt="image" src="https://github.com/user-attachments/assets/440d195b-cac4-4b94-bf9f-25fec5ce6233" />












<img width="921" height="640" alt="image" src="https://github.com/user-attachments/assets/75d11b44-e87f-4c7a-ae9b-57aeec68da59" />















<img width="625" height="418" alt="image" src="https://github.com/user-attachments/assets/38d4ee59-1698-449f-8cdf-9738fd2ae085" />















<img width="1266" height="652" alt="image" src="https://github.com/user-attachments/assets/d45f8f79-8775-4809-8b23-3f2c2557545f" />


















<img width="1212" height="49" alt="image" src="https://github.com/user-attachments/assets/acf4a92d-5918-47e6-9ef0-aeb762c92c6e" />




### Networks for how containers can be managed

Bridge Network: Default network mode for containers on the same machine. Containers on the bridge network can communicate with each other using thier own IP addresses. Isolated from the host machine network providing an extra layer of security. 


Host Network - 



## Linking containers together 
So far, I have built a genuine web application using flask. Now will be linking flask to mySQL database. How to link multiple containers together alloweing them to interact with each other seamlessly. 




<img width="1471" height="732" alt="image" src="https://github.com/user-attachments/assets/c0103d34-7680-4e1b-acac-64e7a68d14d2" />







<img width="1911" height="1020" alt="image" src="https://github.com/user-attachments/assets/8a8bdec9-5b54-44de-83fc-86b3f7b30e60" />







<img width="1235" height="415" alt="image" src="https://github.com/user-attachments/assets/b184a442-c043-48ef-842f-d2e79ea9c836" />








docker run -d --name mydb --network my-custom-network -e MYSQL_ROOT_PASSWORD=my-secret-pw mysql:5.7







docker run -d --name myapp --network my-custom-network -p 5002:5002 hello-flask-mysql







## Using DockerHub


First created a DockerHub account and created a repository where I can store my images. Made it public facing too. 





<img width="1883" height="838" alt="image" src="https://github.com/user-attachments/assets/34e0f86f-56b6-4485-91ae-0e2797ad6180" />








Used the "docker login" command to be able to access my dockerhub account in the command line. 




<img width="918" height="162" alt="image" src="https://github.com/user-attachments/assets/62e53cc6-5e1d-4ac0-b18e-096cad3018b6" />





I then built the image of my dockerfile and tagged it with my username/repository. I named the tag "v1". Used the dot at the end of the command to use the current directory as the build context.





<img width="1916" height="1036" alt="image" src="https://github.com/user-attachments/assets/caaf072c-8049-48bc-9644-a7fc5842bbc7" />










I then used dockerpush to upload my image to dockerhub. Basically it is uploading my image to dockerhub under the specified repository name. 




<img width="999" height="253" alt="image" src="https://github.com/user-attachments/assets/982d03a4-bafe-4f3a-a3f3-e5d793fb5fa1" />





Can see that my image is there now: 






<img width="1174" height="685" alt="image" src="https://github.com/user-attachments/assets/6acc1c34-4cb8-4617-ba87-c230d36b8105" />








Can also pull the image down to another machine using docker pull which will upload it to your local machine. 






<img width="970" height="139" alt="image" src="https://github.com/user-attachments/assets/e600c0cb-8b4f-4978-83ec-79540733ce90" />





## Pushing an Amazon ECR Image 








<img width="1494" height="448" alt="image" src="https://github.com/user-attachments/assets/230d8a77-75ad-432b-a458-052178783952" />















<img width="1479" height="503" alt="image" src="https://github.com/user-attachments/assets/1dbfda6a-5b8a-4b66-87e9-c5036aed1023" />















<img width="1587" height="835" alt="image" src="https://github.com/user-attachments/assets/ba40673e-5b20-462a-83e3-690c19ffb90e" />


















<img width="825" height="670" alt="image" src="https://github.com/user-attachments/assets/6fc4fec9-ac77-46cd-870e-6930ef8ed843" />













<img width="825" height="670" alt="image" src="https://github.com/user-attachments/assets/043ac7e5-b3a1-4685-a810-f684a3fe138f" />














<img width="806" height="358" alt="image" src="https://github.com/user-attachments/assets/ed2506d3-e877-4c5c-ba88-9c23492a15a2" />





















