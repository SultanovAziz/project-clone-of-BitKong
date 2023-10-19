# Bitkong Simulator
My project is a simulator one of the game in online casino game Bitkong. The goal of this project is to provide users with an authentic experience of playing Bitkong in a virtual environment. 
With this project, users can enjoy playing Bitkong without leaving their homes. The main features of the project include the ability to play Bitkong, display graphical elements of the game, and process the results. We have also added some unique features such as enhanced graphical effects and additional bonuses to make the gameplay even more engaging.


# Er-diagram and his attribute present 
```mermaid
erDiagram
    User ||--o{ Game : plays
    Game ||--|{ GameLevel : has
    User ||--o{ ClientSeed : has
    User ||--o{ ServerSeed : has
    ClientSeed ||--o{ Game : uses
    ServerSeed ||--o{ Game : uses
    Game ||--o| TopWin : is
    User ||--o{ Account : has
    Account }o--|| Currency : in
    Account ||--o{ Transaction : has 
    User {
        int id PK
        varchar Login
        varchar Password
        varchar FirstName
        varchar LastName
        varchar Email
        varchar Phone
        varchar Role
        datetime DateCreate
        datetime DateUpdate
    }
    ClientSeed {
        int id PK
        int UserID FK
        varchar Hash
        datetime DateCreate
        datetime DateUpdate
    }
    ServerSeed {
        int id PK
        int UserID FK
        varchar Hash
        datetime DateCreate
        datetime DateUpdate
    }
    Game {
        int id PK
        int UserID FK
        int ClientSeed FK
        int ServerSeed FK
        varchar Name
        int Bet

        varchar Status
        datetime DateCreate
        datetime DateUpdate

    }
    GameLevel {
        int id PK
        int GameID FK
        datetime DateCreate
        datetime DateUpdate

    }
    TopWin {
        int id PK
        int GameID FK
        datetime DateCreate
        datetime DateUpdate
    }
    Account {
        int id PK
        int UserID FK
        datetime DateCreate
        datetime DateUpdate

    }
    Currency {
        int id PK
        
        datetime DateCreate
        datetime DateUpdate

    }
    Transaction {
        int id PK

        datetime DateCreate
        datetime DateUpdate
        
    }
