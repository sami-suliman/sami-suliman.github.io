---
layout: post
title:      "JavaScript and Rails Project – Manufacturing Tracker Application"
date:       2020-02-15 23:18:00 +0000
permalink:  javascript_and_rails_project_manufacturing_tracker_application
---


For my JavaScript and Rails portfolio project at Flatiron School, I decided to build an application that track the assembly of a product at the production floor. For this project I brought Ruby and JavaScript together, I used JavaScript for my frontend and rails for my backend.

In this app I created two separate repositories, the first repository for the backend (Ruby on Rails) and the second repository for the frontend (JavaScript). The Rails backend represent the APIs that needed for the JavaScript frontend. For communicating with the server I used RESTful in the Rails API, and fetch with appropriate HTTP verb in JavaScript frontend.  I was initially struggling with using fetch, so I am writing here how I used fetch in JavaScript to send a request and get information from the server. 

Fetch is method that available in the global window scope. It’s use to retrieves data. It’s the most efficient way to make requests to the server without reloading the web page. The simple HTTP request with fetch: 
 
```
fetch(url)
        .then(function(response) {
          return response.json();
        })
        .then(function(json){
          // code to do DOM manipulation
        });
```

Here the examples for using fetch in my project: 

**“GET” Requests:** 

I used “GET” to tell the backend to send some information to the frontend:

```
 fetch(`${BASE_URL}drawings`)
        .then(response => response.json())
        .then(json => {
            
          json.forEach(drawingObj => {
            
            const newdrawing = new Drawing(drawingObj);
            newdrawing.render();
          })
        })
```
 
**“POST” Requests: **

I used “POST” to supply the backend with some parameters:

```
         fetch(`${BASE_URL}drawings`, {
             method: "POST",
             headers: {
                 "Content-Type": "application/json",
                "Accept": "application/json,",
                "credentials": "include"
            },
            body: JSON.stringify({drawing})
        })
        .then(response => response.json())
        .then(function(object){
            const drawing = new Drawing(object);
            drawingContainer.innerHtml += drawing.render;
            form.innerHTML = ""
        })
        .catch(err => console.log(err))
      }
```
 
**“DELETE” Requests: **

I used “DELETE” to tell the backend to remove a piece of data:

```
        fetch(BASE_URL + `drawings/${event.target.parentElement.id}`, {
        method: "DELETE",
        headers: {
          "Content-Type": "application/json",
          "Accept": "application/json"
        }
      })
      .then(event.target.parentElement.remove())
```
 
.
