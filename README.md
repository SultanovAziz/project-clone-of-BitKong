# project-clone-of-BitKong
Clone one of game in bitkong.com



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
