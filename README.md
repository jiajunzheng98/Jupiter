# Take it - Event Search and Ticket Recommendation

An interactive web application for users to search events by their geolocations and get recommendations based on their favorites.(Events are fetched from TicketMaster API)

## Tech Stack
* Front end: HTML/CSS/JavaScript
* Back end: JAVA
* Database: MYSQL MongoDB
* Java servlet: Apache Tomcat
* Test: Apache JMeter

## Structure
![alt text](/images/ticket1.png)

## Logic layer
![alt text](/images/ticket2.png)

## RPC
Java servelet handles:
* login
* logout
* register
* search items
* recommend items
* set/unset favorite items

## Recommendation Algorithm(content-based)
In this project, I recommend events based on categories that the user has favorited. By knowing the category of the item the user favorited, I recommend some events belong to this category nearby this user. 

Concrete steps are as follow:
* Fetch all ids of these events this user has visited.
* Given all these events, fetch the categories of these events. 
* Given these categories, find what are the events that belong to them. 
* Filter events that this user has visited. 
* Sort the recommendation list on ascending order of distance between recommended events's locations and user's location.



## Database
Used MySQL to store real business data (price, location, category, etc.) and migrated to NoSQL database (MongoDB) for better scalability

### MySQL database schema:
![alt text](/images/ticket3.png)
