# hello_flyway_postgres
- Hello flyway with postgres
- Start db
```bash
docker-compose up -d db
```
- Migrate
```bash
- docker-compose run --rm flyway migrate
```
- Display info
```bash
- docker-compose run --rm flyway info
```
- Database dump
```bash
- docker-compose exec db pg_dump app -U postgres -s > pg_dump.txt
```
- URL from database tool
    - localhost:5433
    - user: postgres
    - password: 1234
    - URL: jdbc:postgresql://localhost:5433/postgres