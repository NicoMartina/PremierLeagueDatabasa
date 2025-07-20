# Premier League Database

A Spring Boot REST API for managing Premier League player statistics, including detailed info such as nationality, position, team, and key performance metrics.

---

## Table of Contents

- [Project Overview](#project-overview)  
- [Features](#features)  
- [Technologies](#technologies)  
- [Getting Started](#getting-started)  
- [API Endpoints](#api-endpoints)  
- [Data Model](#data-model)  
- [Usage Examples](#usage-examples)  
- [Contributing](#contributing)  
- [License](#license)  

---

## Project Overview

This backend application allows you to **store, retrieve, update, and delete** Premier League player data. You can filter players by various parameters such as team, position, nationality, or name via RESTful endpoints.

---

## Features

- Manage detailed player statistics  
- Filter players by team, position, nationality, or name  
- CRUD operations: Create, Read, Update, Delete players  
- Built with Spring Boot and Spring Data JPA  

---

## Technologies

- Java 17+  
- Spring Boot  
- Spring Data JPA  
- Hibernate / Jakarta Persistence (JPA)  
- Lombok  
- SQL Database (e.g., H2, MySQL, PostgreSQL)  

---

## Getting Started

### Prerequisites

- Java JDK 17 or newer  
- Maven or Gradle  
- SQL database setup or use embedded H2 for testing  

### Run Locally

1. Clone the repo:
   ```bash
   git clone https://github.com/yourusername/premier-league-database.git
   cd premier-league-database
Build the project:
./mvnw clean install
Configure your database connection in src/main/resources/application.properties.
Run the app:
./mvnw spring-boot:run
The API will be running at:
http://localhost:8080
API Endpoints

Method	Endpoint	Description	Query Parameters
GET	/players	Retrieve players (all or filtered)	team, name, position, nation (optional)
POST	/players	Add a new player	JSON body with player details
PUT	/players	Update an existing player	JSON body with updated player
DELETE	/players/{playerName}	Delete a player by name	Path variable: playerName
Data Model

Player Entity
Field	Type	Description
name	String	Player's name (Primary Key)
nation	String	Player's nationality
position	String	Player's position
age	Integer	Player's age
matches_played	Integer	Number of matches played
starts	Integer	Number of starts
minutes_played	Double	Total minutes played
goals	Double	Number of goals scored
assists	Double	Number of assists
penalties_scored	Double	Number of penalties scored
yellow_cards	Double	Number of yellow cards
red_cards	Double	Number of red cards
expected_goals	Double	Expected goals metric
expected_assists	Double	Expected assists metric
team_name	String	Player's team name
Usage Examples

Get all players
GET /players
Get players by team and position
GET /players?team=Arsenal&position=Forward
Add a new player
POST /players
Content-Type: application/json

{
  "name": "John Doe",
  "nation": "England",
  "position": "Midfielder",
  "age": 25,
  "matches_played": 30,
  "starts": 28,
  "minutes_played": 2500.0,
  "goals": 5.0,
  "assists": 7.0,
  "penalties_scored": 1.0,
  "yellow_cards": 3.0,
  "red_cards": 0.0,
  "expected_goals": 4.5,
  "expected_assists": 6.0,
  "team_name": "Arsenal"
}
Update a player
PUT /players
Content-Type: application/json

{
  "name": "John Doe",
  "team_name": "Arsenal",
  "position": "Midfielder",
  "nation": "England"
  // other fields can be updated similarly
}
Delete a player
DELETE /players/John Doe
Contributing

Feel free to fork the repository, open issues, and submit pull requests for improvements.
License

This project is licensed under the MIT License.

---

Just save this text as `README.md` in your project root folder. That’s it! If you want, I 
