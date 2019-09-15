---
layout: post
title:      "The Process of CLI Data Gem Project "
date:       2019-09-15 21:32:41 +0000
permalink:  the_process_of_cli_data_gem_project
---


When I started my Online Software Engineering program at Flatiron School and after I read the curriculum, I began wondering how I am going to be building a Ruby CLI data gem project from scratch after only one month from starting this program? Knowing that I didn’t have any coding experience before, which it was make me very nervous at the beginning of starting the project. 

I am working at Medical device company, so I decided to build my first  project to be related to my company. For this project I decided to build a CLI Gem application that help the customers to grab the medical devices information out of the company website by use scraping technique and give them the option to place their order online. The following steps describe the process of my CLI Gem Data Project: 

Step (1)  Install Bundler Gem: 
I installed bundler gem in my terminal by writing the following line: 

```
bundle gem stryker_services
```

Step (2)  Add executable file:
I got my project files to be executable by placing the following line in my bin directory:

```
#!/usr/bin/env ruby
```

Step (3) File requirement: 
I got all files have access to one another: 

```
require 'open-uri'
require 'nokogiri'
require 'pry'

require_relative "./stryker_services/version"
require_relative "./stryker_services/cli"
require_relative "./stryker_services/scraper"
require_relative "./stryker_services/equipment"
require_relative "./stryker_services/order"
```

Step (4) Create CLI Application :
-	Create command line interface cli file: lib/stryker_services/cli.rb
-	Define Cli class
-	Define instance method call run that include: 
•	Puts "Welcome to The Communications Division at Stryker".
•	 Show the list of Equipment’s:
•	 Ask the customer : “Please select an equipment from the list to see the description”.
•	Give back more detail about the equipment that the customer need.
•	 After getting all info about the equipment, ask the customer to fill their order info: (Name, Hospital name, Contact, qty).
•	 Goodbye "Your order has been successfully processed!" , "Thanks for shopping with us online!"

Step (5)  Scraping:
In order to grab the medical devices information out of the company website ("https://www.stryker.com/us/en/portfolios/medical-surgical-equipment/infrastructure-and-room-design/ed.html/")  I used the nokogiri gem: 

```
doc = Nokogiri::HTML(html) 
```

-	Create scraper file: lib/stryker_services/scraper.rb 
-	  Define Scraper class: 
-	  Define instance class call self.scrape_equipment
•	 Get equip_name and url data.
•	 Create new instance base on the information that get scrape. 
 
 Step (6) Store equipments data:
-	 Create equipments file: lib/stryker_services/equipment.rb
-	 Define Equipment class:
•	Store information in respective class (  attr_accessor ).
•	Create  class variable that equal to an empty array.
•	Define .new instance method ( initialize ) .
•	Store new instance that got Create into class variable array.
•	Access equipments : define new method self.all.

Step (7) Place an Order:
-	Create order file: lib/stryker_services/order.rb
-	 Define Order class:
•	 Store information in respective class (  attr_accessor ).
•	Create class variable that equal to an empty array.
-	Store new instance that got create into class variable array.
-	 Access orders: define new method self.all.


Despite all the struggles that I had during the process of building this project, I feel that I learn a lot. I am grateful that I went through this experience, because I believe making mistakes and getting struggle are a part of learning process.  

