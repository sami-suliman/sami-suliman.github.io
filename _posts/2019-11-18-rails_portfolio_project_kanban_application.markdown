---
layout: post
title:      "Rails Portfolio Project – Kanban Application"
date:       2019-11-18 12:43:10 -0500
permalink:  rails_portfolio_project_kanban_application
---


For my Rails portfolio project, I decided to borrow the theme‘Kanban application’ from my Sinatra project, but it rebuilt from scratch. My Sinatra project was built by a basic CRUD MVC app that using ActiveRecord, while Rails project is built through complex forms and RESTful routes. 

Kanban is a Japanese term that mean signboard. It uses in lean manufacturing to help improve manufacturing efficiency. With this app assemblers can create a secure registration using email, or Github login. After login assemblers  can create, edit, and delete their parts request. Also, it shows the whorehouse pickers a list of parts that need to be pickedand then marked as picked.
The following steps describe the process of buildingKanban App Project: 

User Authentication: 
•	Signup, Login and Logout:
I used  devise gem to create a secure registration
•	Login with other service:
For registration using third party app I used github-omniauth

Model:
•	User Model:
-	Has many orders
-	Attributes: email, password

•	Order Model:
-	Belongs to user
-	Has many partorders
-	Has many parts through partorders
-	Attributes: station and user_id

•	Partorder Model:
-	Belongs to order
-	Belongs to part
-	Attributes: qty and picked

•	Part Model:
-	Has many partorders
-	Has many orders through partorders

