---
toc: true
comments: false
layout: post
title: Final Project Individual Code 
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

```python
/* Background images for different sections */
        .bgimg-1, .bgimg-2, .bgimg-3, .bgimg-4, .bgimg-5 {
            position: relative;
            opacity: 0.65;
            background-attachment: fixed;
            background-position: center;
            background-repeat: no-repeat;
            background-size: cover;
        }
```
This CSS code defines styles for creating a parallax effect with background images on a webpage. The sections, identified by classes like .bgimg-1 to .bgimg-5, have a slightly transparent background (opacity: 0.65) for a subtle see-through effect. The background-attachment: fixed; property ensures the images remain fixed while scrolling, creating the parallax effect. The images are centered both horizontally and vertically (background-position: center;), and they do not repeat (background-repeat: no-repeat;). The background-size: cover; property ensures the images cover the entire container, maintaining their aspect ratio. Together, these styles contribute to an aesthetically pleasing parallax scrolling experience on the webpage.

Here is our [final product](https://deeskili.github.io/RocketSimFrontend/)

# Pulling Backend Data to the Frontend

Saathvik from the backend team developed the backend servers. These servers feature a URL link hosting an extensive collection of over 4000 recipes. Each recipe is accompanied by detailed instructions on how to recreate the dish and a list of required ingredients. We employed two APIs, both related to the same recipe database. One API encompasses the entirety of all recipes, while the other is ID-linked, allowing users to modify the ID in the URL for access to a specific recipe. The integration of these URL APIs ensures the functionality of the recipe manager search.

As a part of the frontend team, we first needed to know how to pull the backend data to the frontend. So while Saathvik was working on the backend api. Sri and I were trying to figure out how to fetch data from backend to front end. We first practiced by trying to fetch data through another similar api (Edamam). 

```python
import requests

APP_ID = '9d5f6314'
APP_KEY = '6402f0a5647c2c2bb72cb3bb592d0c8b'

api_endpoint = 'https://api.edamam.com/search'
```

The first line imports the requests module, which is a popular Python library for making HTTP requests. It allows you to send HTTP requests and receive responses from web servers. The module simplifies the process of interacting with web services and APIs

The next two lines define the API credentials (specially the App ID and App Key) required to authenticate and access the Edamam Recipe Search API. Essentially gives you access to the api and allows you to extract data from it with code.

The endpoint URL for an API provided by Edamam is involved in the making of requests to the Edamam API for search operations.

```python
params = {
    'q': 'chicken',  
    'app_id': APP_ID,
    'app_key': APP_KEY,
}
response = requests.get(api_endpoint, params=params)
```
These lines define the api parameters. In this case, the script is searching for recipes containing the keyword 'chicken', and it includes the App ID and App Key for authentication. To change the search, you just need to change the keywords in the 'q' parameter. On the final project, we were able to make changes to the 'q' parameter through an interactive search bar, which allows users to search up any recipe they want.

The next line sends a GET request to the Edamam API using the specified endpoint and parameters. The response is stored in the response variable.

```python
if response.status_code == 200:
    data = response.json()
    for hit in data.get('hits', []):
        recipe = hit.get('recipe', {})
        print(f"Recipe: {recipe.get('label')}")
        print(f"Ingredients: {', '.join(recipe.get('ingredientLines', []))}")
        print(f"URL: {recipe.get('url')}")
        print("\n" + "=" * 30 + "\n")
else:
    print(f"Error: {response.status_code} - {response.text}")
```

This block checks if the API request was successful (status code 200). If successful, it parses the JSON response and prints information about each recipe, including its label, ingredients, and URL. If there's an error, it prints the error status code and response text.

# Recipe List

The recipe list page is our main work. This page contains all the 4000+ recipes inside recipe card. These cards are formtatted previously and all the data within them is dynamically generated. The CSS and HTML for the card acts as a templete onto which all the recipes are extracted from and displayed on. The HTML and CSS element is then linked with the JS element down below which then extracts data from the URL API and outputs them into the recipes own card.

Here's what I worked on:

```python
// Function to fetch and display the recipes from the API
            function fetchAndDisplayRecipes() {
                const apiUrl = "https://backendrocketmain.stu.nighthawkcodingsociety.com/api/recipe/recipes";
                // this is our main API from which all the recipe cards are formatted. 
                // This is one of the two major API that we will be using for our NATM projec , the first is our main API conatining all the recipes, the second the same API but this time fromatted with the API ID, recipe 1 has the ID of 1 and so on....
                fetch(apiUrl)
                    .then(response => {
                        if (!response.ok) {
                            throw new Error(`Network response was not ok: ${response.status}`);
                        }
                        return response.json();
                    })
                    .then(data => {
                        // Generate recipe cards for each recipe
                        // Generate recipe cards for each recipe. Each of the 4000+ recipes have their own recipe cards as formatted above with the css code
                        data.forEach(recipe => {
                            const recipeCard = createRecipeCard(recipe); // creates a recipe card for each of the recipe title extracted and links to each div section and thus the term "dynamically generated cards".
                            recipeList.appendChild(recipeCard);
                        });
                    })
                    .catch(error => {
                        console.error("There was a problem fetching the data:", error); // for corrupted data the program outputs a 404 error notification
                    });
            }
```

The JavaScript code defines a function named fetchAndDisplayRecipes that fetches recipe data from a specified API endpoint and dynamically generates recipe cards for each retrieved recipe. The API endpoint is set in the apiUrl variable, and the fetch function is used to make a network request. The code handles response errors and parses the JSON data. For each recipe in the data, the createRecipeCard function is called to generate a recipe card, which is then appended to the recipeList element. The code also includes error handling to log any issues with the data retrieval process. Overall, the function facilitates the dynamic creation and display of recipe cards based on data fetched from the API.

```python
searchInput.addEventListener("input", performSearch);

```

This line of code adds an "input" event listener to a search input field in a web page. When a user types or modifies the input, the designated performSearch function is triggered, suggesting that the code is designed to respond dynamically to user input, likely initiating a search operation. The details of the search functionality are expected to be implemented within the performSearch function elsewhere in the code.

# Issues
- The first issue we faced was trying to copy the code from the figma design into vscode, but we then realized that that was not going to be possible as figma is just a site that helps create stuff and outline stuff and not for code. & thus as outlined above with the help of w3 school we built of webpage as it is today.

- The second issue we faced was trying to extract data from the backend API URL into the frontend website. With a little help from ChatGPT we fixed the issue with the cont apiUrl function as well as the element fetch solution provided by the AI tool.

```python
Issue 2
function fetchAndDisplayRecipes() {
                const apiUrl = "https://backendrocketmain.stu.nighthawkcodingsociety.com/api/recipe/recipes";
```

- The third issue we faced was linking the recipe details and the recipe list pages or in API tems linking the first and second API and displaying the correct data for the correct recipe all the while the entire website is API controlled

- We fixed this error by first commiting the recipe details page and copying that link into the recipe list page. This helped link both pages together no matter if it was a localhost or a commited site. with the {recipeID} fucntion, the code could dynamically generate the correct ID and display the correct recipe by details.



```python
Issue 3
function createRecipeDetailsPage(recipe) {
     window.location.href = `https://deeskili.github.io/RocketSimFrontend/c4.1/2023/10/21/recipedetails.html?recipeId=${recipe.id}`;
```

- The fourth and only unresolved issue was with our images. Our images are downloaded into the images/Food Images file. Our main issue with these image is with linking them onto the wbesite. No matter what we try they dont seem to come into the site Our trial fixes included

    - Trying to link the images through the API itself
    - Trying to link the image using an external API
    - Trying to link the image by librares from google
    - Trying to use another API to link the images 

# GitHub analytics review

Error: Regarding the shared Github repository. Since this was my first time using vscode, I wasn't really familiar with this tool, so when my group worked together using a shared Vscode, I ran into a lot of issues. The main one being that a lot of times I forgot to git pull before committing, which lead to me having to reclone the repository multiple times. To avoid these issues, our group had to have good communication regarding commits and git pulls.

Key Commit: My favorite commit was [adding comments to the recipe list code](https://github.com/Deeskili/RocketSimFrontend/commit/bd70d8919ec68684c501d73414fbf918ba289f41). This really allowed me to understand what was going on in the code from each event listener to each individual function involved in creating the recipe cards. It also allowed me to catch up on my partner Sri's work and understand what he was working on and what he was trying to achieve with each line of code. Doing this allowed us to find errors and fix mistakes.
























