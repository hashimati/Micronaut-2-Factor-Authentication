# Micronaut-2-Factor-Authentication

This is a simple project that demonstrats the Two Factor Authentication in the Micronaut. The security code is a customization from the **Security-JWT** generated code in **[MicroCli](https://github.com/hashimati/MicroCli)** tool. 

## Overview
1. The application is a Micronaut application that stores the users-details and refresh-token in **H2** database. 
2. The application creates an **admin** user on startup event with password "admin". 
3. **Login URL**: http://localhost:8080/api/users/login , **Method**: POST, **Request Body**: {"username":admin, "password":"admin"}. 
4. On success login trial, the application will log the **OTP** on the console to simulate sending email or SMS. Please check **OTPService.java**. 
5. The new OTP is valid for **5 Minutes**. 
6. **Verify URL**: http://localhost:8080/api/users/verify, **Method**: POST, **Request Body**: {"username":"admin", "password":<Received OTP>}. 
7. The response of the verification is the JWT token. 


## To Run The Application. 
```Shell
  > gradlew run
```
 
  
Happy Coding :)

