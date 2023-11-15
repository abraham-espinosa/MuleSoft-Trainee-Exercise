# Exercise 1 - Hello Mule
Build your first Hello Mule application using Anypoint Studio, and deploy it locally and to CloudHub.  
It is required:  
* MuleSoft's IDE - https://www.mulesoft.com/lp/dl/anypoint-mule-studio  
* REST Client Postman - https://www.postman.com/downloads/  
* CloudHub account - https://anypoint.mulesoft.com/login/signup  

## Table Content 
1. [Getting Started](#1-Getting-Started)
2. [Create a Project in Anypoint Studio](#2-create-a-project-in-anypoint-studio)
3. [HTTP Listener Connector](#3-http-listener-connector)
4. [Set Payload](#4-set-payload)
5. [Run the Application Locally](#5-run-the-application-locally)
6. [Deploy the Project into CloudHub](#6-deploy-the-project-into-cloudhub)
   
## Getting Started
**MuleSoft’s IDE**  
* Download Anypoint Studio (MeluSoft’s IDIE) from https://www.mulesoft.com/lp/dl/anypoint-mule-studio  
* Extract the downloaded folder **close to your root** to avoid possible errors  
* Open AnypointStudio application.  
![0000](https://github.com/abraham-espinosa/mulesoft-trainee-exercise/assets/60346436/acd9afa9-d68a-4fad-beb6-861e808c4fad)  

**Postman**  
* Download and install a REST client platform as Postman from https://www.postman.com/downloads  ]
   
**CloudHub**  
* Sign up for Anypoint Platform from https://anypoint.mulesoft.com/login/signup to host your applications on CloudHub.   

## 1. Create a Project in Anypoint Studio
*	Create a new Mule project by clicking on **File** > **New** > **Mule Project**, then enter the project name **HelloMule** and click on Finish  
![1 0](https://github.com/abraham-espinosa/mulesoft-trainee-exercise/assets/60346436/2d2cf52b-f5d3-493f-ac31-14eb909f3033)  
![1 1](https://github.com/abraham-espinosa/mulesoft-trainee-exercise/assets/60346436/e78ccf3e-1f3c-4cf8-b7d4-ede5c627b43e)  
*	A new blank project called **hellomule** is created  
  
## 2. HTTP Listener Connector
*	Go to the Mule Palette, select the HTTP module, then drag and drop the Listener into the canvas area  
![1 3](https://github.com/abraham-espinosa/mulesoft-trainee-exercise/assets/60346436/68ac443d-2ea2-47ee-88db-c4a5b034eca4)    
*	Select the new hellomuleFlow from de canvas area and click on the HTTP Listener. Go to the Properties Editor area, then go into the Basic Settings configuration and click the Green Plus button  
![1 3 5](https://github.com/abraham-espinosa/mulesoft-trainee-exercise/assets/60346436/57698be8-274f-42d2-8a36-a31c3e60a8bc)  
*	Leave all default configurations for the HTTP Listener **Host: 0.0.0.0** and **Port: 8081**, then click on the OK button  
![1 5](https://github.com/abraham-espinosa/mulesoft-trainee-exercise/assets/60346436/b206a212-662d-4dbe-90cc-9656c60f6a37)  
* Go into the general path section and enter **/hellomule**  
![1 5 2](https://github.com/abraham-espinosa/mulesoft-trainee-exercise/assets/60346436/c8c77a30-a562-485c-adb3-7eee012f7593)  
* Do not forget to save the project constantly to see reflected the changes  
![1 7](https://github.com/abraham-espinosa/mulesoft-trainee-exercise/assets/60346436/140306d4-9d3f-4ed6-9ad2-0d3e28b25341)  

## 3. Set Payload
* Go to the Mule Palette, select the Core module, then drag and drop the **Set Payload** into the hellomuleFlow that already exists in the canvas area  
![1 8 - Copy](https://github.com/abraham-espinosa/mulesoft-trainee-exercise/assets/60346436/94a5001e-7e06-411f-a9eb-07a5eb1ac647)  
* Go to the Properties Editor area, then go into the Settings section, check out the fx button, and enter the value **Hello Mule**  
![1 6](https://github.com/abraham-espinosa/mulesoft-trainee-exercise/assets/60346436/7bc548f5-138d-43ed-bc70-548de5410836)    

## 4. Run the Application Locally
* Run it locally by right-clicking into the Canvas area and select **Run project hellomule**  
![1 8](https://github.com/abraham-espinosa/mulesoft-trainee-exercise/assets/60346436/e9810627-28ee-48bb-b6a9-b0b046aea280)  
* Look for the **DEPLOYED STATUS** in the console, meaning that the application is running and does not contain errors  
![1 9](https://github.com/abraham-espinosa/mulesoft-trainee-exercise/assets/60346436/02dd6095-4437-4696-a0d1-084ed436c448)  
* Test the application using a REST Client platform (Postman). Create a new request by clicking on New, then select the **HTTP** icon  
![1 9 5](https://github.com/abraham-espinosa/mulesoft-trainee-exercise/assets/60346436/ee4ca1f9-6487-403c-8663-5e1acba7485e)  
* Enter **0.0.0.0:8081/hellomule** or **localhost:8081/hellomule** as the URL, then click on Send to see the response Hello Mule and a 200 OK status  
![1 11](https://github.com/abraham-espinosa/mulesoft-trainee-exercise/assets/60346436/a8e7ddff-906d-4d4d-b6e7-1faa91354834)  
* Go to the console and click the **Red** button to stop the application 
![1 12](https://github.com/abraham-espinosa/mulesoft-trainee-exercise/assets/60346436/845f9f0b-852a-4661-bf12-541682b64f9e)  

## 5. Deploy the Project into CloudHub 
* Go to the package explorer and right-click on the project’s root (hellomule), then select **Anypoint Platform** > **Deploy to CloudHub**  
![1 13](https://github.com/abraham-espinosa/mulesoft-trainee-exercise/assets/60346436/fefb2ef9-e846-4f32-8747-66e6ba956044)  
* Enter username and password for Anypoint Platform account  
![1 14](https://github.com/abraham-espinosa/mulesoft-trainee-exercise/assets/60346436/d90c85c2-df9f-4e3e-b2ad-7983d54df524)  
* Choose the SandBox environment, leave all default configurations, and click on Deploy Application  
![1 15](https://github.com/abraham-espinosa/mulesoft-trainee-exercise/assets/60346436/43be4ad5-29e2-45bc-bb60-342005813f48)  
* Go to https://anypoint.mulesoft.com and login again (if it is required). Click on the **left menu** > **Manager Center** > **Runtime Manager**  
![1 16](https://github.com/abraham-espinosa/mulesoft-trainee-exercise/assets/60346436/c990693b-d71c-4943-b768-00f14594a80c)  
* Choose again the **SandBox** environment  
![1 17](https://github.com/abraham-espinosa/mulesoft-trainee-exercise/assets/60346436/22917889-410d-46d3-bbc2-3724b057dcfc)  
* Details about the application is shown like the **Running Status**  
![1 18](https://github.com/abraham-espinosa/mulesoft-trainee-exercise/assets/60346436/e22422a2-8f64-41bb-82ea-442bf258b515)  
* Click on the hellomule name to see more details, then copy the Public EndPoint URL **https://hellomule-dl8v0b.5sc6y6-3.usa-e2.cloudhub.io**  
![1 19](https://github.com/abraham-espinosa/mulesoft-trainee-exercise/assets/60346436/33dbbbfb-485a-4317-b113-bf0e3d7260bb)  
* Go back to Postman and enter only **hellomule-dl8v0b.5sc6y6-3.usa-e2.cloudhub.io/hellomule** as the new URL instead of 0.0.0.0:8081/hellomule or localhost:8081/hellomule, then click on **Send**  
![1 20](https://github.com/abraham-espinosa/mulesoft-trainee-exercise/assets/60346436/1063ad76-623a-4359-8dab-9bd0385733a1)  

