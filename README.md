# Exercise 2 – Set Up Global Elements and Properties Files in Anypoint Studio 
Apply best practices to keep global elements. Set up the hardcoded values into properties and the Configuration Properties global  
It is required:  
* MuleSoft's IDE - https://www.mulesoft.com/lp/dl/anypoint-mule-studio  
* REST Client Postman - https://www.postman.com/downloads/  
* Previous code from `exercise1/hello-mule` branch

## Table Content 
1. [Set Up Global Elements](#1-Set-Up-Global-Elements)
2. [Set Up Properties](#2-Set-Up-Properties)
3. [Implement Properties into Global Elements](#3-Implement-Properties-into-Global-Elements)
4. [Test the Application](#4-Test-the-Application)

## 1. Set Up Global Elements
*	Go to the package explorer and right-click on the project’s root (hellomule), then select **New**** > **Mule Configuration File**. Enter `global.xml` as the file name  
*	Go to the configuration xml tab from the hellomule.xml file, then cut the **http listener config**  
![1](https://github.com/abraham-espinosa/mulesoft-trainee-exercise/assets/60346436/a0fbac21-8faf-4935-b936-a29b43a76802)  
* Paste it into the `global.xml` file, inside of the `<mule>` tag  
![2](https://github.com/abraham-espinosa/mulesoft-trainee-exercise/assets/60346436/240170dd-fa48-4e84-9d6e-d705235f4dd0)  
*	Click on Save All, then go to the Global Elements tab from the `global.xml` file to see the HTTP Listener config  
![3](https://github.com/abraham-espinosa/mulesoft-trainee-exercise/assets/60346436/ecae5148-b9d0-4b1b-87f9-ffcbf121045b)  

## 2. Set Up Properties 
*	Go to the package explorer and right-click on **src/main/resources** > **New** > **File** to create a **local properties file** to be used for our local environment. Enter `local.properties` as the file name and click on Finish  
![5](https://github.com/abraham-espinosa/mulesoft-trainee-exercise/assets/60346436/7da27564-24ae-4cbc-b22d-558c35a387a6)  
*	Add the following properties to it:  
```
http.listener.host=0.0.0.0
http.listener.port=8081
```  
![7](https://github.com/abraham-espinosa/mulesoft-trainee-exercise/assets/60346436/60adbad6-a791-4888-a938-4e657ad1cca9)  
*	Create another file for our **dev environment** to be used in CloudHub. Enter `dev.properties` as the file name and click on Finish  
*	Add the same properties to this file:  
```
http.listener.host=0.0.0.0
http.listener.port=8081
```  
![8](https://github.com/abraham-espinosa/mulesoft-trainee-exercise/assets/60346436/9bb69fc1-8a5a-48c1-a214-ca536b707d1c)  


## 3. Implement Properties into Global Elements
*	Copy **http.listener.host** and past it in the Host field with the following format:  
`${http.listener.host}`  
*	Copy **http.listener.port** and past it in the Port field with the same format, once done, click on OK:  
`${http.listener.port}`  
![9](https://github.com/abraham-espinosa/mulesoft-trainee-exercise/assets/60346436/c645fb13-07ba-43fd-ab6b-2dda5e0623d8)  
*	MuleSoft requires us to add other configurations to implement our properties. Go to the Global Elements tab from the global.xml file, then click on **Create**  
![10](https://github.com/abraham-espinosa/mulesoft-trainee-exercise/assets/60346436/d7737f4b-5720-4356-876d-720c5a0a86f9)  
*	Search for ***configuration properties*** and select it, then click on OK  
![11](https://github.com/abraham-espinosa/mulesoft-trainee-exercise/assets/60346436/91f2618e-0b4b-4c90-8373-2e42f1130890)  
*	Add `${env}.properties` as the values so it can be changed dynamically depending on which environment is being used  
![12](https://github.com/abraham-espinosa/mulesoft-trainee-exercise/assets/60346436/63c9bc9c-1e39-4cfa-8e3f-abf056c2d793)  
*	Click on Create, then search for ***global property*** and select it  
*	Enter `env` as the name and `local` as the value, this will allow the runtime to know when it is running in a local environment  
![14](https://github.com/abraham-espinosa/mulesoft-trainee-exercise/assets/60346436/637667d7-0bd3-4407-b454-677ae47f22df)  

## 4. Test the Application 
*	Run project `hellomule` from canvas to deploy the application in local  
![15](https://github.com/abraham-espinosa/mulesoft-trainee-exercise/assets/60346436/072c8135-db35-4c04-a2dc-483c0a16da21)  
![16](https://github.com/abraham-espinosa/mulesoft-trainee-exercise/assets/60346436/6ef3cfde-9e71-488a-ac3e-45ce42360147)  
*	Test the application using a REST Client platform (Postman) using `localhost:8081/hellomule` as the URL. Click on Send to see the response `Hello Mule` and a 200 OK status  
![17](https://github.com/abraham-espinosa/mulesoft-trainee-exercise/assets/60346436/99e2078f-1084-48dc-93f1-709cab53a805)  


