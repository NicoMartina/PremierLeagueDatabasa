# Premier League Database

A Spring Boot REST API for managing Premier League player statistics.

---

## Getting Started

### Build the project

Run the following command in your terminal:

    ./mvnw clean install

### Configure Database

Edit `src/main/resources/application.properties` to configure your database connection.

### Run the Application

Start the application with:

    ./mvnw spring-boot:run

The API will be accessible at: `http://localhost:8080`

---

## API Endpoints

| Method | Endpoint               | Description                          | Query Parameters                  |
|--------|------------------------|------------------------------------|---------------------------------|
| GET    | `/players`             | Retrieve players (all or filtered) | `team`, `name`, `position`, `nation` (all optional) |
| POST   | `/players`             | Add a new player                   | JSON body with player details   |
| PUT    | `/players`             | Update an existing player          | JSON body with updated player   |
| DELETE | `/players/{playerName}`| Delete a player by name            | Path variable: `playerName`     |

---

## Data Model

**Player Entity**

| Field             | Type    | Description                     |
|-------------------|---------|--------------------------------|
| `name`            | String  | Player's name (Primary Key)     |
| `nation`          | String  | Player's nationality            |
| `position`        | String  | Player's position               |
| `age`             | Integer | Player's age                   |
| `matches_played`   | Integer | Number of matches played        |
| `starts`          | Integer | Number of starts                |
| `minutes_played`   | Double  | Total minutes played            |
| `goals`           | Double  | Number of goals scored          |
| `assists`         | Double  | Number of assists               |
| `penalties_scored`| Double  | Number of penalties scored      |
| `yellow_cards`    | Double  | Number of yellow cards          |
| `red_cards`       | Double  | Number of red cards             |
| `expected_goals`  | Double  | Expected goals metric           |
| `expected_assists`| Double  | Expected assists metric         |
| `team_name`       | String  | Player's team name              |

---

## Usage Examples

### Get all players

GET /players

### Get players by team and position

GET /players?team=Arsenal&position=Forward

### Add a new player

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

### Update a player

PUT /players
Content-Type: application/json
{
"name": "John Doe",
"team_name": "Arsenal",
"position": "Midfielder",
"nation": "England"
// other fields can be updated similarly
}
