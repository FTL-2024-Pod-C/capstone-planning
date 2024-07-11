# Project Plan

Pod Members: **Julia Chaidez Karina Perez Madel Sibal**

## Problem Statement and Description

In the United States, restaurants generate 22 to 33 billion pounds of food waste annually contributing significantly to economic challenges. Concurrently, approximately one in eight households face food insecurity or lack access to nutritious meals.

The main purpose of this website is to ensure that restaurants ethically dispose of their waste to food pantries in need of nutritious donations. Restaurants can upload their leftover food and food pantries can view such listings and make requests based on their needs.

## User Roles and Personas

Restaurant: a user who owns or manages a food establishment and wishes to donate surplus food to food pantries in need.

Food Pantry: a user representing an organization dedicated to distributing food to individuals and families in need, seeking donations of surplus food from restaurants.

Restaurant Persona 1: Emma owns a small restaurant in Portland, Oregon, specializing in dishes sourced from local farms. Emma is able to manage administrative tasks on her computer but prefers hands-on operations in her kitchen. Her motivation stems from a deep commitment to reducing food waste and supporting her community. Emma sees donating surplus food to food pantries as a way to make a positive impact. She is concerned about logistical challenges in coordinating donations and ensuring food safety regulations.

Restaurant Persona 2: Carlos manages a family-owned diner in Miami, Florida. At 60 years old, Carlos is less comfortable with technology, mainly using his smartphone for basic communications. Despite this, Carlos shares Emma's passion for giving back to the community. He sees donating excess food from his diner as a meaningful way to contribute to the fight against food insecurity in Miami. Carlos faces challenges in managing time and resources to coordinate donations effectively while navigating concerns about liability and food preservation.

Food Pantry Persona 1: Grace oversees a nonprofit food pantry in Chicago, Illinois, serving a diverse community in need of regular food assistance. Grace is able  to use both a computer and smartphone for managing pantry operations. Her motivation is driven by a strong commitment to ensuring her pantry consistently provides nutritious food to their clients. Grace actively seeks donations from local restaurants to supplement their food stock and meets challenges in managing fluctuating food supplies and coordinating logistics efficiently.

Food Pantry Persona 2: Michael runs an outreach center in Los Angeles, California, dedicated to providing meals and support services to homeless individuals. Michael is moderately comfortable with technology, preferring face-to-face interactions for community outreach. His motivation stems from a deep empathy for the homeless population in LA. Michael relies on regular food donations from local restaurants to meet the high demand for meals at his center. He struggles with challenges such as limited resources for transportation and storage of perishable food items, as well as navigating local regulations to ensure compliance and efficiency in food donation logistics.

## User Stories

1. **As a restaurant, I want to create a profile on the website, so that I can showcase my establishment and provide information about the types of surplus food I have available for donation.**

2. **As a restaurant, I want to receive notifications when a food pantry requests a donation, so that I can promptly review and respond to donation requests.**

3. **As a restaurant, I want to track my inventory of surplus food and update availability on the website in real-time, so that food pantries can make informed donation requests**

4. **As a restaurant, I want to filter food pantries by location and specific needs (e.g., dietary restrictions), so that I can target my donations more effectively.**

5. **As a restaurant, I want to maintain a record of donations made to different food pantries, including dates and quantities, so that I can track my community impact and compliance with regulations.**

6. **As a food pantry, I want to search for nearby restaurants that have surplus food available, so that I can request donations that align with the nutritional needs of our clients.**

7. **As a food pantry, I want to see the donation history of a restaurant, including types and quantities of food donated, so that I can assess the reliability and suitability of donations.**

8. **As a food pantry, I want to rate and provide feedback on donations received from restaurants, so that I can share the quality of service and food with other pantries.**

9. **As a food pantry, I want to be matched automatically with restaurants based on our specific food needs and preferences, so that I can streamline the donation process and reduce search time.**

10. **As a food pantry, I want to receive automated reminders or alerts when new donations are available from restaurants in our area, so that we can promptly arrange pickups and reduce food waste.**

## Pages/Screens

Landing Page
Interactive Login & Sign-Up
Meet the Founders
Restaurant Dashboard
View Profile
Update Listings
Donation History
Food Pantry Dashboard + Food Available Page
View Profile
Restaurant List

Link to wireframe:
`https://www.figma.com/design/T3s5bBSqb0c49lHmk9dZdw/Leftover-Love?node-id=0-1&t=fUAFR4UwJSv4q8eu-1`

## Data Model

## Restaurant Model

| Column Name   | Type          | Description   |
| ------------- | ------------- | ------------- |
| id  | int  | Primary key  |
| name  | string  | Name of the restaurant  |
| location  | string  | Restaurant address  |
| description  | string  | Description of the restaurant (whatever the restaurant user puts in when creating their profile)  |
| email  | string  | Restaurant email  |
| phone number  | string  | Restaurant phone number  |
| rating  | float  | What the restaurant is rated based on the food pantry’s feedback  |
| profile photo  | string (url)  | Restaurants can set their profile photo  |

## Food Pantry Model

| Column Name   | Type          | Description   |
| ------------- | ------------- | ------------- |
| id  | int  | Primary key  |
| name  | string  | Name of the food pantry  |
| location  | string  | Food Pantry address  |
| description  | string  | Description of the food pantry (whatever the food pantry user puts in when creating their profile)  |
| email  | string  | Food pantry email  |
| phone number  | string  | Food pantry phone number  |
| profile photo  | string (url)  | Food pantries can set their profile photo  |


## Listing Model

| Column Name   | Type          | Description   |
| ------------- | ------------- | ------------- |
| id  | int  | Primary key  |
| name  | string  | What the food item is is (ex. bananas)  |
| quantity  | int  | How many of the item is available  |
| unit  | string  | What unit of measurement the listing is in (pounds, numerical amount, etc.)  |
| description  | string  | Description of the food item (whatever the restaurant user puts in when uploading a listing)  |
| expiration date  | string  | Food items spoil so an expiration date is important. This will help with prioritizing items that must be requested as soon as possible  |
| category  | string  | What category the food item falls into (dairy, meat, vegetable, etc.)  |
| photo  | string (url) | Photo of the food item  |
| restaurant_id  | int | Used to associate the listing with the restaurant that uploads it  |


## Request Model

| Column Name   | Type          | Description   |
| ------------- | ------------- | ------------- |
| id  | int  | Primary key  |
| date  | DateTime  | Date of when the request was made  |
| status  | string  | Indicates whether a request is pending approval from a restaurant, the request has been approved, and fulfilled  |
| food_pantry_id  | int  | Used to associate a request with the food pantry that made it  |

## Request Items Model

| Column Name   | Type          | Description   |
| ------------- | ------------- | ------------- |
| id  | int  | Primary Key  |
| quantity  | int  | How much the food pantry wants of that particular item  |
| listing_id  | int  | Used to associate a requested item to what listing it was made pulled from (for shopping cart purposes)  |
| request_id  | int  | Used to associate a requested item to the specific request it was made from  |

## Review Model

| Column Name   | Type          | Description   |
| ------------- | ------------- | ------------- |
| id  | int  | Primary key  |
| rating  | float  | Food pantries can leave reviews based on how their experience with the restaurant’s donation went  |
| date  | DateTime  | Date of when the review was made  |
| description  | string  | Food pantries can write further details about their experience  |
| food_pantry_id  | int  | Used to associate a review with whatever food pantry left it  |
| restaurant_id  | int  | Used to associate a review with the restaurant it pertains to  |

## API Endpoints

| CRUD          | HTTP Verb     | Description   | Model this applies to   |
| ------------- | ------------- | ------------- | ----------------------- |
| Content Cell  | Content Cell  | Content Cell  | Content Cell            |
| Content Cell  | Content Cell  | Content Cell  | Content Cell            |

| CRUD      | HTTP Verb | Description                                                                 | Models this applies to                      |
|-----------|-----------|-----------------------------------------------------------------------------|--------------------------------------------|
| CREATE    | POST      | - add a restaurant                                                           | Restaurant                                 |
|           |           | - add a listing                                                              | Listings                                   |
|           |           | - add a food pantry                                                          | Food Pantry                                |
|           |           | - add a request                                                               | Request                                    |
|           |           | - add a request item                                                          | Request Items                              |
|           |           | - add a review                                                                | Reviews                                    |
|           |           | - add a request item to a particular request                                  | Request Items                              |
| READ      | GET       | - fetch all restaurants                                                      | Restaurant, fetching by ID                 |
|           |           | - fetch all food pantries                                                    | Food Pantry, fetching by ID                |
|           |           | - fetch all listings                                                         | Listings, fetching by restaurant ID        |
|           |           | - fetch all requests                                                         | Request, fetching by ID                    |
|           |           | - fetch all request items                                                    | Request Items, fetching by ID              |
|           |           | - fetch all reviews                                                          | Reviews, fetching by restaurant ID         |
| UPDATE    | PUT       | - update a restaurant                                                        | Restaurant                                 |
|           |           | - update a food pantry                                                       | Food Pantry                                |
|           |           | - update a listing                                                           | Listings                                   |
|           |           | - update a request                                                           | Request                                    |
|           |           | - update a request item                                                      | Request Items                              |
|           |           | - update a review                                                            | Reviews                                    |
| DELETE    | DELETE    | - deleting a restaurant                                                      | Restaurant                                 |
|           |           | - deleting a food pantry                                                     | Food Pantry                                |
|           |           | - deleting a listing                                                         | Listings, deleting from a particular restaurant |
|           |           | - deleting a request                                                         | Request                                    |
|           |           | - deleting a review                                                          | Reviews                                    |
|           |           | - deleting a request item                                                    | Request Items                              |
|           |           | - deleting a request item from a particular request                          | Request Items                              |

