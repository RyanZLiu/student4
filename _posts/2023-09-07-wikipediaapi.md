---
toc: true
comments: false
layout: post
title: Wikipedia API
description: Search anything up on wikipedia!
type: tangibles
courses: { compsci: {week: 3} }
---

<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Wikipedia Search</title>
</head>
<body>
    <h1>Wikipedia Search</h1>
    <input type="text" id="searchInput" placeholder="Enter your search term">
    <button onclick="searchWikipedia()">Search</button>
    <div id="searchResults"></div>

    <script>
        function searchWikipedia() {
            const searchInput = document.getElementById("searchInput").value;
            const searchResults = document.getElementById("searchResults");

            // Clear previous search results
            searchResults.innerHTML = "";

            // Make a request to the Wikipedia API
            fetch(`https://en.wikipedia.org/w/api.php?action=opensearch&format=json&search=${searchInput}&origin=*`)
                .then(response => response.json())
                .then(data => {
                    const titles = data[1];
                    const descriptions = data[2];
                    const links = data[3];

                    // Display search results
                    if (titles.length > 0) {
                        for (let i = 0; i < titles.length; i++) {
                            const result = document.createElement("div");
                            result.innerHTML = `
                                <h2><a href="${links[i]}" target="_blank">${titles[i]}</a></h2>
                                <p>${descriptions[i]}</p>
                            `;
                            searchResults.appendChild(result);
                        }
                    } else {
                        searchResults.innerHTML = "No results found.";
                    }
                })
                .catch(error => {
                    console.error("Error fetching data from Wikipedia API:", error);
                    searchResults.innerHTML = "An error occurred while fetching data.";
                });
        }
    </script>
</body>
</html>
