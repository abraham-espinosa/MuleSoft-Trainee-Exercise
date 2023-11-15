# Exercise 3 – Secure Properties Before Deployment  
Create secure property files to store private keys or information that is reused throughout the application. 
It is required:  
* MuleSoft's IDE - https://www.mulesoft.com/lp/dl/anypoint-mule-studio  
* REST Client Postman - https://www.postman.com/downloads/  
* CloudHub account - https://anypoint.mulesoft.com/login/signup
* Previous code from **exercise2/global-elements-properties** branch

# Set Up Global Elements
* Go to the package explorer and right-click on **src/main/resources** > **New** > **File**, then enter `local.secure.properties` as the file name, click on Finish  
* Go to the package explorer and right-click on **src/main/resources** > **New** > **File**. then enter `dev.secure.properties` as the file name, click on Finish  
* Add the following properties in the `local.secure.properties` file:  
```
example.username=myUsernameLocal
example.password=myPasswordLocal
```
* Do the same for the `dev.secure.properties` file:
```
example.username=myUsernameDev
example.password=myPasswordDev
```  
![1](https://github.com/abraham-espinosa/mulesoft-trainee-exercise/assets/60346436/9a083f56-25b9-4ba6-af24-533870d5aa46)  
* Go into `hellomule.xml file`, then go to the Mule Palette and click on **Search in Exchange**  
* Search for ***mule secure configuration properties***, then click on Add and Finish  
![2](https://github.com/abraham-espinosa/mulesoft-trainee-exercise/assets/60346436/1e312f0d-2c98-44aa-b1f3-eb0a27233606)  
* Go to the Global Elements tab from `global.xml` file, then click on Create, search for Secure Properties Config and select OK   
![3](https://github.com/abraham-espinosa/mulesoft-trainee-exercise/assets/60346436/b2a666f5-f69d-46e5-b34d-392e2bcdc689)  
* Set File field as `${env}.secure.properties`, set Key field as `${secure.key}`, and select `Blowfish` for the Algorithm field  
![4](https://github.com/abraham-espinosa/mulesoft-trainee-exercise/assets/60346436/91649d1e-b1cb-4f6c-ae0e-2efadb458e73)  
* Leave all the rest as default and click on OK  
* Go again into `hellomule.xml` file, then go to the Mule Palette, drag and drop the **Logger** into the canvas flow next to the Set Payload component  
![5](https://github.com/abraham-espinosa/mulesoft-trainee-exercise/assets/60346436/541d91a9-11ec-49b8-a125-6a10ef2fb9d2)  
* Click on the `fx` button from the Logger properties, then click on the mapping button.  
![6](https://github.com/abraham-espinosa/mulesoft-trainee-exercise/assets/60346436/dcc8410a-666e-46ef-a340-f1a69501bb08)  
* Inside of the new view, add the following DataWeave code and click on Done to save it
```
output application/java
---
"Username: " ++ Mule::p("secure::example.username")
++ " - " ++
"Password: " ++ Mule::p("secure::example.password")
```  
![8](https://github.com/abraham-espinosa/mulesoft-trainee-exercise/assets/60346436/187ca6ab-b98c-42b4-879d-825e70a085e8)  
 
## Encrypt Properties 
* Go to https://docs.mulesoft.com/mule-runtime/latest/secure-configuration-properties#secure_props_tool **Mule Runtime** > **Security** > **Secure Configuration Properties**   
* Download `Secure Properties Tool Jar File`  
![9](https://github.com/abraham-espinosa/mulesoft-trainee-exercise/assets/60346436/35999dab-02af-4165-9364-ab012c2420b3)  
* Go into the console and navigate to the path file. Use the following format code by copying and pasting it in the console:  
```
java -cp secure-properties-tool.jar com.mulesoft.tools.SecurePropertiesTool \
string \
encrypt \
Blowfish \
CBC \
mulesoft \
"some value to encrypt"
```  
* Once copied, enter `MyMuleSoftKey` instead of mulesoft to add the password that it will be used to encrypt the property  
* Add the actual value of the property `“myUsernameLocal”`. If you have problems using the previous format code, you can use the following:  
`java -cp secure-properties-tool.jar com.mulesoft.tools.SecurePropertiesTool string encrypt Blowfish CBC MyMuleSoftKey "myUsernameLocal"`  
![10](https://github.com/abraham-espinosa/mulesoft-trainee-exercise/assets/60346436/0de05ea7-a7bb-4162-bfd2-29c51a30006c)  
* Copy the encrypted property and past it into the `local.secure.properties` file with the following format `![HbsuWJRjiubchmzQREGdsA==]`  
![11](https://github.com/abraham-espinosa/mulesoft-trainee-exercise/assets/60346436/69154e8c-9523-4064-a12f-ab7c8cb37818)  
* Repeat the previous process for the rest of the properties  
![12](https://github.com/abraham-espinosa/mulesoft-trainee-exercise/assets/60346436/1f0d5bbc-7815-42b0-a670-198577ea5f0f)  
![13](https://github.com/abraham-espinosa/mulesoft-trainee-exercise/assets/60346436/19634fa1-2be3-4397-939f-cfbf67153c21)  

  
## Test the Application Locally 
* Right-click on **hellomule** > **Run As** > **Run Configurations** > **Environment**  
* Click on Add, then add `secure.key` as the name and `MyMuleSoftKey` as the value. Click on Apply, then select Run  
![14](https://github.com/abraham-espinosa/mulesoft-trainee-exercise/assets/60346436/93d829f3-b0f6-4b94-8a41-d4d77503420c)  
![15](https://github.com/abraham-espinosa/mulesoft-trainee-exercise/assets/60346436/2bd55c74-630e-4245-b6b0-d819436ed81c)  
* Test the application using a REST Client platform (Postman) using `localhost:8081/hellomule` as the URL  
* In addition to the `Hello Mule` body and 200 OK status, in the mule console is displayed the username and password local   
![16](https://github.com/abraham-espinosa/mulesoft-trainee-exercise/assets/60346436/1c9df662-9f00-4869-a14e-22caf37f9682)  


## Deploy to CloudHub
* Open `mule-artifact.json` file, then add `“secureProperties”: [“secure.key”]` to hide our `secure.key` property in the Runtime Manager  
![17](https://github.com/abraham-espinosa/mulesoft-trainee-exercise/assets/60346436/8231115d-d7ef-4d6a-81a1-1ee058c9192e)  
* Right-click in **hellomule** > **Anypoint Platform** > **Deploy to CloudHub**  
* Select Overwrite Existing Application checkbox in order to replacer the previous application if it is asked  
* Go into **properties** tab, then add `env` as key and `dev` as value, also add `secure.key` as the key and `MyMuleSoftKey` as the value. Click on Deploy Application   
![18](https://github.com/abraham-espinosa/mulesoft-trainee-exercise/assets/60346436/91b031db-6bff-4849-9319-ef6b7a04f38f)  
* Go back to Postman and enter `hellomule-dl8v0b.5sc6y6-3.usa-e2.cloudhub.io/hellomule` as the new URL, then click on Send  
* Hello Mule is displayed with a 200 OK status, additionally in the Runtime Manager Logs is displayed the logs with the username `myUsernameDev` and password `myPasswordDev`  
![19](https://github.com/abraham-espinosa/mulesoft-trainee-exercise/assets/60346436/49a56155-5bc9-4395-b972-76f433642027)  
