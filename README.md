# Exercise 5 – Apply Client ID Enforcement Policies
Apply the Client ID enforcement policy to secure our Mule app with basic authentication.  
It is required:  
* REST Client Postman - https://www.postman.com/downloads/
* CloudHub account - https://anypoint.mulesoft.com/login/signup
* Previous code from `exercise4/api-autodiscovery` branch

## Table Content 
1. [Set the Client ID Policy using API Manager](#1-Set-the-Client-ID-Policy-using-API-Manager)
2. [Test the Application ](#2-Test-the-Application)
3. [Generate Credentials ](#3-Generate-Credentials)

## 1. Set the Client ID Policy using API Manager
* Go to **API Manager** in https://anypoint.mulesoft.com, then open the API and select **Policies** from the left menu
* Select **Add Policy**  
![1](https://github.com/abraham-espinosa/mulesoft-trainee-exercise/assets/60346436/c53c32cc-e728-4a28-a362-b9fd65a7e759)
* Select **Basic Authentication – Simple** and click on Next  
![2](https://github.com/abraham-espinosa/mulesoft-trainee-exercise/assets/60346436/7f3b430d-654b-4ad3-beac-a7f0314a5f11)
* Click on Advanced options and make sure it is selected the latest version. Select Apply configurations to all API methods & resources, then select Apply  
![3](https://github.com/abraham-espinosa/mulesoft-trainee-exercise/assets/60346436/b0d7b733-449c-4137-886e-cf7d711657c0)

## 2. Test the Application 
* Test the application using Postman with the URL from CloudHub. It will be displayed an authentication error.
![4](https://github.com/abraham-espinosa/mulesoft-trainee-exercise/assets/60346436/e0287a32-5685-4305-96f6-9235440ba79e)

## 3. Generate Credentials 
* Go to **Anypoint Platform** and select **Exchange** 
* Select **hellomuleapi** from the Assets section, then on the right side click on **Request Access**  
![5](https://github.com/abraham-espinosa/mulesoft-trainee-exercise/assets/60346436/63557b2d-dd4a-4ec9-8dfb-46335f0933ac)  
![6](https://github.com/abraham-espinosa/mulesoft-trainee-exercise/assets/60346436/432e1fe0-34d8-4655-bfd8-13d4335d0a61)  
* Choose the API instance that was recently created  
![7](https://github.com/abraham-espinosa/mulesoft-trainee-exercise/assets/60346436/1e93bbd6-8d29-4d48-9b3e-2f434c45a827)  
* Select Create a new application for the Application field if it is the first time you have selected it. Enter `hellomuleapp` as the Application Name and select Create  
![8](https://github.com/abraham-espinosa/mulesoft-trainee-exercise/assets/60346436/2ed05a87-a48b-45f9-857b-48a263555990)  
* Select hellomuleapp as the Application and click on Request Access    
![9](https://github.com/abraham-espinosa/mulesoft-trainee-exercise/assets/60346436/4cbaef10-e7b6-406e-81c4-5e0c5a6de2a4)  
* Copy the `Client ID` and `Client Secret`, then past the `Client ID` as Username and `Client Secret` as Password in the Auth tab (Basic Auth) from Postman and select Send  
![10](https://github.com/abraham-espinosa/mulesoft-trainee-exercise/assets/60346436/72a4f29d-9d3c-49e7-a156-6e5f7d1136bc)
