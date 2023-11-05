---
toc: true
comments: false
layout: post
title: Edamam Api
type: tangibles
courses: { compsci: {week: 11} }    
---

# Overview of my Final Project
Our ultimate project entails a recipe manager book that retrieves information from a backend API and showcases the results on the frontend webpage. The backend server houses a collection of more than 4000 recipes, which our code fetches and presents as recipe cards. These cards allow users to easily search and select any recipe that catches their fancy. Since my focus was on the frontend aspect of the project, I'll be summarizing my entire journey leading up to the completion of this endeavor.

# Planning Process
In Week 0, we kicked off by brainstorming ideas for our recipe manager website. Initially, we aimed for a rocket simulator, but we changed our plan to a recipe manager because making and running a rocket simulator turned out to be too tricky. We would've needed to make the calculations for the physics of a rocket launch, which isn't a feasible project. For the frontend team during Week 0, our primary focus was to plan and create the homepage. We first mapped it out using Figma and then wrote the code based on our design. Our aim was to add a cool parallax effect to the scrolling, thinking it would make the website more enjoyable to explore.

[Link to Figma Animation](https://www.figma.com/proto/3nvtE8kJLdDL6zx4ho8bp8/Recipe-Book-Manager?node-id=23-30&starting-point-node-id=23%3A30)

# Front Page Designing
At first, we tried to implement and embed our figma design into our vscode so that it would show up on github, but we soon realized that that wasn't possible, so then we created another design based on our original figma design

![parallaxbackgroundimages](images/parallaxbackgroundimages.png)

This CSS code defines styles for creating a parallax effect with background images on a webpage. The sections, identified by classes like .bgimg-1 to .bgimg-5, have a slightly transparent background (opacity: 0.65) for a subtle see-through effect. The background-attachment: fixed; property ensures the images remain fixed while scrolling, creating the parallax effect. The images are centered both horizontally and vertically (background-position: center;), and they do not repeat (background-repeat: no-repeat;). The background-size: cover; property ensures the images cover the entire container, maintaining their aspect ratio. Together, these styles contribute to an aesthetically pleasing parallax scrolling experience on the webpage.

Here is our [final product](https://deeskili.github.io/RocketSimFrontend/)

# Pulling Backend Data to the Frontend

Saathvik from the backend team developed the backend servers. These servers feature a URL link hosting an extensive collection of over 4000 recipes. Each recipe is accompanied by detailed instructions on how to recreate the dish and a list of required ingredients. We employed two APIs, both related to the same recipe database. One API encompasses the entirety of all recipes, while the other is ID-linked, allowing users to modify the ID in the URL for access to a specific recipe. The integration of these URL APIs ensures the functionality of the recipe manager search.

As a part of the frontend team, we first needed to know how to pull the backend data to the frontend. So while Saathvik was working on the backend api. Sri and I were trying to figure out how to fetch data from backend to front end. We first practiced by trying to fetch data through another similar api (Edamam). 

![codepart1](images/part1.png)

The first line imports the requests module, which is a popular Python library for making HTTP requests. It allows you to send HTTP requests and receive responses from web servers. The module simplifies the process of interacting with web services and APIs

The next two lines define the API credentials (specially the App ID and App Key) required to authenticate and access the Edamam Recipe Search API. Essentially gives you access to the api and allows you to extract data from it with code.

The endpoint URL for an API provided by Edamam is involved in the making of requests to the Edamam API for search operations.

![codepart2](images/part2.png)

These lines define the api parameters. In this case, the script is searching for recipes containing the keyword 'chicken', and it includes the App ID and App Key for authentication. To change the search, you just need to change the keywords in the 'q' parameter. On the final project, we were able to make changes to the 'q' parameter through an interactive search bar, which allows users to search up any recipe they want.

The next line sends a GET request to the Edamam API using the specified endpoint and parameters. The response is stored in the response variable.

![codepart3](images/part3.png)

This block checks if the API request was successful (status code 200). If successful, it parses the JSON response and prints information about each recipe, including its label, ingredients, and URL. If there's an error, it prints the error status code and response text.






















