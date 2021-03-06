# Cinema-app
#### This project is a simulator of cinema tickets app.
#### The application allows to add movies, movies sessions, cinema halls, register new users with different roles, make order of the tickets.
## Depending on the user's roles, he will have access to different endpoints:
#### Without roles:
- ``` POST|GET: /login ``` - login page
- ``` POST: /register ``` - register page *(JSON - {"email":"alice@gmail.com", "password":"12345678", "repeatPassword":"12345678"})*

#### Only for admin role:
- ``` GET: /users/by-email``` - get information about user by his email *(RequestParam - ?email=alice@gmail.com)*
- ``` POST: /cinema-halls``` - add new cinema hall *(JSON - {"capacity":200, "description":"first floor"})*
- ``` POST: /movies``` - add new movie *(JSON - {"title":"Scary movie", "description":"USA"})*
- ``` POST: /movies-sessions``` - add new movie session  *(JSON - {"movieId":1, "cinemaHallId":1, "showTime":"23.01.2022 20:00"})*
- ``` PUT: /movies-sessions/{id}``` - update movie session by id
- ``` DELETE: /movies-sessions/{id}``` - delete movie session by id

#### Only for user role:
- ``` GET: /orders``` - get all orders from DB 
- ``` GET: /shopping-carts/by-user``` - get shopping cart of current customer 
- ``` POST: /orders/complete``` - complete order of current user 
- ``` PUT: /shopping-carts/movie-sessions``` - add movie session by id to shopping cart of current customer (RequestParam - ?movieSessionId=3)

#### For both roles:
- ``` GET: /cinema-halls``` - get all cinema halls from DB
- ``` GET: /movies``` - get all movies from DB
- ``` GET: /movie-sessions/available``` - get movie session by movie id and show time *(RequestParam - ?movieId=1&date=23.01.2022)*
- ``` GET: /movie-sessions/{id}``` - get information about movie session by id 

## Technologies
- Spring (Core, Web, Security)
- Hibernate
- MySql
- Apache Tomcat
- Maven

## Configure before launch
1. Install MySQL and create schema in DB 
2. Install TomCat 9.05.56
3. Change properties in src/main/resources/db.properties with your data.
4. Launch and enjoy! You'll have default user with admin role:
   email: bob@gmail.com, password: 123456. 