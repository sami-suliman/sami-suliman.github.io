---
layout: post
title:      "React Redux Portfolio Project– Calibration Tools Application"
date:       2020-03-28 23:42:12 +0000
permalink:  react_redux_portfolio_project_calibration_tools_application
---


For my final portfolio project at Flatiron School, I created an application that track the calibration tools due date at the production floor. This application helps an assembler to find which tools need to be sending for calibration before the due date. The app also help to prevent using tools with calibration past due date. For this project I built one HTML page that renders the application using React-Redux with Rails. 

In this application I created two separate repositories, the first repository for the backend (Ruby on Rails) and the second repository for the frontend (React/Redux). The Rails backend represent the APIs that needed for the React/Redux frontend. For communicating with the server I used RESTful in the Rails API, and fetch within actions in React/Redux frontend. 

I used the <create-react-app> generator to start building my frontend. In order to build a Single Page App (SPA) I used React Router to call the components that display the app information. I included 3 routes. The first rout shows the tools calibration due date list. The second rout shows the tool card and allows us to delete or update the tool. The last rout includes the new tool form.    
.
