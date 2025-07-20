#Premier League Database

A Spring Boot application that provides a REST API for managing Premier League player statistics. The project stores detailed player data including their nationality, position, team, and various performance metrics.
Table of Contents

Overview
Features
Technologies
Getting Started
API Endpoints
Data Model
Usage Examples
Contributing
License
Overview

This project is a backend service designed to store, update, retrieve, and delete player statistics for the Premier League. It exposes RESTful endpoints to query players by name, position, nationality, and team, as well as combinations of these attributes.
Features

Store player data with detailed statistics such as goals, assists, cards, minutes played, etc.
Query players by team, position, name, or nationality.
Add, update, and delete player records.
Built using Spring Boot and JPA for easy database integration.
Technologies

Java 17+
Spring Boot
Spring Data JPA
Hibernate / Jakarta Persistence (JPA)
Lombok (for boilerplate code reduction)
RESTful API
Any SQL-based database (e.g., H2, MySQL, PostgreSQL)
Getting Started

Prerequisites
Java Development Kit (JDK) 17 or higher
Maven or Gradle build tool
SQL Database setup (or use embedded H2 for development)
Build and Run
Clone the repository:
git clone https://github.com/yourusername/premier-league-database.git
cd premier-league-database
Build the project:
./mvnw clean install
Configure your application.properties or application.yml for database connection.
Run the application:
./mvnw spring-boot:run
The API will be available at http://localhost:8080.
API Endpoints

Method	Endpoint	Description	Query Parameters
GET	/players	Get all players or filtered players	team, name, position, nation (all optional)
POST	/players	Add a new player	Player JSON in request body
PUT	/players	Update an existing player	Player JSON in request body
DELETE	/players/{playerName}	Delete a player by name	Path variable: playerName
Data Model

Player Entity
Field	Type	Description
name	String	Player's name (Primary Key)
nation	String	Player's nationality
position	String	Player's playing position
age	Integer	Player's age
matches_played	Integer	Number of matches played
starts	Integer	Number of starts
minutes_played	Double	Total minutes played
goals	Double	Number of goals scored
assists	Double	Number of assists
penalties_scored	Double	Penalties scored
yellow_cards	Double	Number of yellow cards
red_cards	Double	Number of red cards
expected_goals	Double	Expected goals metric
expected_assists	Double	Expected assists metric
team_name	String	Name of the team the player belongs to
Usage Examples

Get all players:
GET /players
Get players by team and position:
GET /players?team=Arsenal&position=Forward
Add a new player:
POST /players
Content-Type: application/json

{
  "name": "John Doe",
  "nation": "England",
  "position": "Midfielder",
  "age": 25,
  "matches_played": 30,
  "starts": 28,
  "minutes_played": 2500,
  "goals": 5,
  "assists": 7,
  "penalties_scored": 1,
  "yellow_cards": 3,
  "red_cards": 0,
  "expected_goals": 4.5,
  "expected_assists": 6.0,
  "team_name": "Arsenal"
}
Update a player:
PUT /players
Content-Type: application/json

{
  "name": "John Doe",
  "team_name": "Arsenal",
  "position": "Midfielder",
  "nation": "England"
  // other fields as needed
}
Delete a player:
DELETE /players/John Doe
Contributing

Contributions are welcome! Please fork the repository and submit pull requests for improvements or bug fixes.
License

This project is licensed under the MIT License.
