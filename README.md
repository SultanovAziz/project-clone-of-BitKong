# Bitkong Simulator
My project is a simulator one of the game in online casino game Bitkong. The goal of this project is to provide users with an authentic experience of playing Bitkong in a virtual environment. 
With this project, users can enjoy playing Bitkong without leaving their homes. The main features of the project include the ability to play Bitkong, display graphical elements of the game, and process the results. We have also added some unique features such as enhanced graphical effects and additional bonuses to make the gameplay even more engaging.


## Diagrams
In this section, you will find the conceptual diagram and logical diagram that describe the architecture and logic of our project:
1. Conceptual Diagram - This diagram presents the overall concept and structure of the project, showing the key components and their interactions.
2. Logical Diagram - This diagram provides a more detailed description of the logic and interactions of the project's components.

### [Conceptual Diagram](#conceptual)
```mermaid
erDiagram   
    user ||--o{ game : plays
    game ||--|{ GameLevel : has
    user ||--o{ client_seed : has
    user ||--o{ server_seed : has
    client_seed ||--o{ game : uses
    server_seed ||--o{ game : uses
    game ||--o| top_win : is
    user ||--o{ account : has
    account }o--|| currency : in
    account ||--o{ transaction : has 
```

### [Logical Diagram](#logical)
```mermaid
erDiagram
    user ||--o{ game : plays
    game ||--|{ GameLevel : has
    user ||--o{ client_seed : has
    user ||--o{ server_seed : has
    client_seed ||--o{ game : uses
    server_seed ||--o{ game : uses
    game ||--o| topwin : is
    user ||--o{ account : has
    account }o--|| currency : in
    account ||--o{ transaction : has 
    user {
        int id PK
        varchar login
        varchar password
        varchar first_name
        varchar last_name
        varchar email
        varchar phone
        varchar role
        datetime date_create
        datetime date_update
    }
    client_seed {
        int id PK
        int user_id FK
        varchar hash
        datetime date_create
        datetime date_update
    }
    server_seed {
        int id PK
        int user_id FK
        varchar hash
        datetime date_create
        datetime date_update
    }
    game {
        int id PK
        int user_id FK
        int client_seed_id FK
        int server_seed_id FK
        varchar name
        int bet

        varchar status
        datetime date_create
        datetime date_update

    }
    GameLevel {
        int id PK
        int game_id FK
        datetime date_create
        datetime date_update

    }
    topwin {
        int id PK
        int game_id FK
        datetime date_create
        datetime date_update
    }
    account {
        int id PK
        int user_id FK
        datetime date_create
        datetime date_update

    }
    currency {
        int id PK
        
        datetime date_create
        datetime date_update

    }
    transaction {
        int id PK

        datetime date_create
        datetime date_update
        
    }
```

