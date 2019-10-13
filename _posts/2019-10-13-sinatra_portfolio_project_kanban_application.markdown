---
layout: post
title:      "Sinatra Portfolio Project – Kanban Application"
date:       2019-10-13 21:15:56 +0000
permalink:  sinatra_portfolio_project_kanban_application
---


Kanban application is my first web app that help assemblers to order their parts just on time from the warehouse. Kanban is a Japanese term that mean signboard. It uses in lean manufacturing to help improve manufacturing efficiency. Kanban App is built by a basic CRUD MVC app that using ActiveRecord with Sinatra. 

I decide to build a simple web app by just using the tools that I have learned so far and at the same time it will meet all the requirements for this project. This app allows assemblers to create, edit, and delete their parts request. Also, it shows the whorehouse pickers a list of parts that need to be picked and then marked as picked. 
The following steps describe the process of building Kanban App Project: 

ActiveRecord: 
By using the ActiveRecorde Migration module I created a series of migrations. 

Model:
I created three models for this project: order, part and user. 
-	Order class has <belongs_to : part> and <belongs_to :user> relationship. 
```
class Order < ActiveRecord::Base
    belongs_to :part
    belongs_to :user
  end
```
-	Part class has <has_many :orders> and <has_many :users, through: :orders> relationship. 
```
class Part < ActiveRecord::Base
    has_many :orders
    has_many :users, through: :orders
end
```
-	Finally, User classe has   <has_many :orders> and <has_many :parts, through: :orders> relationship.
```
class User < ActiveRecord::Base
    has_many :orders
    has_many :parts, through: :orders
    has_secure_password
    validates :username, uniqueness: true
end
```

View: 
I create views for orders, registrations and sessions that help the users to interact with the app.
•	Registrations:
-	SignUp: This form allows the new users to create a username and a password for the first time in order to use the app.
•	Sessions:
-	Login: This form allows the users to login to the app after they create their username and password at signup. 
•	Orders: 
-	Index: This form represents our Kanban board which it shows list of the parts numbers with their status (picked or not picked).
-	New: This form allows the assemblers to request their parts that need to be picked.
-	Show: This form shows the details for one-part request.
-	Edit: This form allows the assemblers to edit their order and warehouse picker change the status from not picked to picked after the part get picked. 

Controllers :
I create an order_controller and sessions_controller which inherit from an application_controller. These two controllers create routes that correspond with the CRUD actions and views.

