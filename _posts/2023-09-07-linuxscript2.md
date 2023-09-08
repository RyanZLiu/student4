---
toc: false
comments: false
layout: post
title: Linux Script
description: Check if everything is installed 
type: tangibles
courses: { compsci: {week: 3} }
---



<html>
<head>
    <title>Check Installed Software</title>
    <style>
        /* Customize the code box styles */
        pre {
            background-color: black;
            color: white;
            border: 1px solid #ccc;
            padding: 10px;
            overflow-x: auto;
            font-family: "Courier New", monospace;
        }
    </style>
</head>
<body>
    <h1>Check Installed Software</h1>
    
    <!-- Code Box -->
    <pre><code>
        check_command() {
            command -v "$1" >/dev/null 2>&1
        }

        check_command "code" && echo "Visual Studio Code is installed" || echo "Visual Studio Code is not installed"

        check_command "brew" && echo "Homebrew is installed" || echo "Homebrew is not installed"

        check_command "python" && echo "Python is installed" || echo "Python is not installed"

        check_command "jupyter" && echo "Jupyter is installed" || echo "Jupyter is not installed"

        check_command "ruby" && echo "Ruby is installed" || echo "Ruby is not installed"

        check_command "jekyll" && echo "Jekyll gem is installed" || echo "Jekyll gem is not installed"

        ruby -v

        python --version

        jupyter --version
    </code></pre>
    
</body>
</html>

