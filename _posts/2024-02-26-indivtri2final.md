---
toc: true
comments: true
layout: post
title: Ryan Liu - Tri 2 Final Individial Review
description: Going over my individual feature(s), the overall project, and College Board requirements.
type: tangibles
courses: { compsci: {week: 10} }
---

## Ryan Liu Trimester 2 Individual Review

# Project Overview

We took inspiration from the canva website and our group created a custom button creator where users could use our websites with built in sliders and options to create a unique button. There are also options to draw lines to create a custom animation for your button. Created buttons can be set as public or private and can be seen through our search page, also allowing for other users to like/dislike public button designs.

# My Feature

My feature is the likes and dislikes that are saved for every button, allowing all users to give their opinion on other users' public buttons.

# Component A: Program

| Collegeboard Requirements | Me |
|------------------|------------------|
| Instructions for input from one of the following: the user, a device, an online datas stream, a file.  | Our Project allows users to click on like or dislike buttons where each click is stored in the backend and updated on the computer.  |
| Use of at least one list (or other collection type) to represent a collection of data that is stored and used to manage program complexity and help fulfill the users purpose.  | I used a sqlite.db database file to store information about each designs like/dislikes. ![Code](https://i.ibb.co/PZz5fRC/Screenshot-2024-02-27-004122.png) |
| At least one procedure that contributed to the program's intened purpose where you have defined: the name, return type, one or more parameters:  | Code that creates like/dislike buttons and updates with each click. ![Code](https://i.ibb.co/3NDnBM5/Screenshot-2024-02-27-010559.png)  |
| An algorithm that includes sequencing, selection, and iteration that is in the body of the selected procedure  | This function shows the sequencing, selection, and iteration through a list of button ids: ![Code](https://i.ibb.co/tBZFVr6/Screenshot-2024-02-27-154219.png) |
| Calls to your student-developed prodcedure:  |  frontend api calls for the obtaining name of button and also for updating likes/dislikes. ![Code](https://i.ibb.co/XVkmxSY/Screenshot-2024-02-27-011709.png)  |
| Instructions for output (tactile, audible, visual, or ) based on input and program functionality  | Success redirects page to see updated like/dislike count. ![Code](https://i.ibb.co/1zBP4fC/Screenshot-2024-02-27-012805.png)  |

# Component B: Video

[Link to Video](https://drive.google.com/file/d/1hdHQzBZHwL3Zw3FdAGimokGt0-sYAoOi/view?usp=drive_link)

| CB Requirements | Me |
|-----------------|----|
| Input to program | Clicking like & dislike buttons. |
| At least one aspect of the functionality of your program | Like and Dislike counts update after respective clicks in the backend. Page reloads after each clicks demonstrating that user clicks were acknowledged |
| Output produced by program | Like and Dislike counts increase after respective clicks |
| My video does not have | Voice narration |
| My video is | In .mp4 format, 1 minute in length, less than 30MB in file size |