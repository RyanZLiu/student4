---
toc: False
comments: True
layout: default
title: DATA STRUCTURES FINAL
description: Ryan Liu AP CSP
courses: {'compsci': {'week': 18}}
---

# Collections 

 - Blog Python Model code and SQLite Database.

 - From VSCode using SQLite3 Editor, show your unique collection/table in database, display rows and columns in the table of the SQLite database.

 - This image shows the sqlite database containing the name of the button, the userID, and the button's likes & dislikes


![image](https://github.com/RyanZLiu/student4/assets/142445209/adef52ea-c37f-40ad-b20e-e0ee09eb099b)

 - From VSCode model, show your unique code that was created to initialize table and create test data.

  - This code is used to create the name formatting name, type, content, userID, likes, dislikes, description with the class Design(db.Model):



![image](https://github.com/RyanZLiu/student4/assets/142445209/b21efc6f-a83a-4117-811d-1e66550f5786)

# Lists and Dictionaries
 - Blog Python API code and use of List and Dictionaries.

 - In VSCode using Debugger, show a list as extracted from database as Python objects.

  - This screenshot is taken in debugger after running the search function. We see multiple Design objects which have been freshly loaded from our database.



![image](https://github.com/RyanZLiu/student4/assets/142445209/d7b1d1d5-34b9-4f22-89b8-fcef6d785acb)


 - In VSCode use Debugger and list, show two distinct example examples of dictionaries, show Keys/Values using debugger.

 - The screenshot is taken in debugger and shows the request body json when saving a design.

![image](https://github.com/RyanZLiu/student4/assets/142445209/95b97892-c3b1-44ea-a7f6-a11b0622e868)

 - The screenshot is taken in debugger and shows the request body json for logging in.
![image](https://ibb.co/7YHhd6y)


# APIs and JSON
 - Blog Python API code and use of Postman to request and respond with JSON.

 - In VSCode, show Python API code definition for request and response using GET, POST, UPDATE methods. Discuss algorithmic condition used to direct request to appropriate Python method based on request method.

  - The screenshot is taken from the users api file and shows the definition of CRUD operations that are run after POST, GET, or PUT requests.

![image](https://github.com/RyanZLiu/student4/assets/142445209/650776f0-72aa-46d2-9f9b-16b8fa5e18ba)


 - In VSCode, show algorithmic conditions used to validate data on a POST condition.

  - The code in the screenshot above checks to see whether certain variables in the request body json are valid or not. If they are, then they will be updated into the user’s entry in the collection in the database.

![image](https://github.com/RyanZLiu/student4/assets/142445209/e000db6a-2511-4b1b-b7d2-ff8b9f09373f)


 - In Postman, show URL request and Body requirements for GET, POST, and UPDATE methods.
 - In Postman, show the JSON response data for 200 success conditions on GET, POST, and UPDATE methods.


![image](https://github.com/RyanZLiu/student4/assets/142445209/feb94b68-900b-4ff4-bf62-f6fa1f3b4a04)
![image](https://github.com/RyanZLiu/student4/assets/142445209/69260be5-1bf9-4884-942f-cd52c77f48fc)
![image](https://github.com/RyanZLiu/student4/assets/142445209/4bb963b5-7a20-44b1-9316-e4726ee67cc3)


 - In Postman, show the JSON response for error for 400 when missing body on a POST request.

![image](https://github.com/RyanZLiu/student4/assets/142445209/4e863779-d836-489d-bb43-9d16c592f2f0)


 - In Postman, show the JSON response for error for 404 when providing an unknown user ID to a UPDATE request.

![image](https://github.com/RyanZLiu/student4/assets/142445209/0e320570-757f-443c-9291-f2fccc9bdab3)

 - Note: In our USER API code, we've set it up so that it automatically fetches the user ID from the JWT token when someone logs in. This means you don't have to include your user ID when you make a PUT request. This way, users can only update their own profiles, and there's no chance of getting a 404 error because there's no unknown user ID involved.


# Frontend
 - Blog JavaScript API fetch code and formatting code to display JSON.

 - In Chrome inspect, show response of JSON objects from fetch of GET, POST, and UPDATE methods.
 - In the Chrome browser, show a demo (GET) of obtaining an Array of JSON objects that are formatted into the browsers screen.
  - The screenshot is taken after running a fetch request to the search endpoint in the backend. The console on the right displays the json data returned by the backend.


![image](https://github.com/RyanZLiu/student4/assets/142445209/2bc20b39-5d92-472d-aa30-fcf636889e06)

 - In JavaScript code, describe fetch and method that obtained the Array of JSON objects.
  - The screenshot shows the frontend displaying multiple objects after iterating through the results provided from the backend.

![image](https://github.com/RyanZLiu/student4/assets/142445209/91b8fadd-2d83-4bbb-9f0a-39c1c238ce48)


 - In JavaScript code, show code that performs iteration and formatting of data into HTML.
  - The screenshot shows the code that allows the frontend to do it.

![image](https://github.com/RyanZLiu/student4/assets/142445209/964ebfe8-879c-4561-aad8-9f2b88f7c756)


 - In the Chrome browser, show a demo (POST or UPDATE) gathering and sending input and receiving a response that show update. Repeat this demo showing both success and failure.

![image](https://github.com/RyanZLiu/student4/assets/142445209/ef047fb5-5682-4d52-b733-cb7f17ecd923)
![image](https://github.com/RyanZLiu/student4/assets/142445209/574abcd0-919a-4aec-b55b-8b08654eaf0c)

 - In JavaScript code, show and describe code that handles success. Describe how code shows success to the user in the Chrome Browser screen.
  - The screenshot shows the browser showing a successful result by alerting the user that the design was saved.


![image](https://github.com/RyanZLiu/student4/assets/142445209/b4fdd394-8c07-4094-8204-4b0785a2a42a)


 - In JavaScript code, show and describe code that handles failure. Describe how the code shows failure to the user in the Chrome Browser screen.

  - The screenshot shows the browser showing an unsuccessful result by alerting the user to 'please enter a design name'.

![image](https://github.com/RyanZLiu/student4/assets/142445209/d1e0d91e-8cb7-423c-9ac9-d22c1d07c73e)


