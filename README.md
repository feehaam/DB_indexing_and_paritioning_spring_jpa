## Practice repo of database indexing and connectionn polling

## Key points
- Postgres DB is used, initialized using docker compose, pgAdmin also added
- 4 different indexing(3 simple, 1 composite) is added on Product entity
- HikaryCP library is used for connection pooling, configurations is added in application.yml

## Running the applcation
- Run docker compose, run spring boot application server, JPA will create the schema
- Log into pgAdmin, register the server
- Copy the query from `product-populate.sql` and run it in our database - it will populate our product table with 1 million data. Note that, I avoided the server side populating as it takes too much time.
- Hit the end point `http://localhost:8080/` - it queries using different indexes and without indexes to show performance. 

Final result looks as bellow (JPA Streamer comparison also added, it's too slow!)
![result.png](src%2Fmain%2Fjava%2Fplayground%2Fdata%2Fresult.png)