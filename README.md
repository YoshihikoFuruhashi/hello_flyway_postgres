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
```bash
Creating hello_flyway_postgres_flyway_run ... done                                                                      Flyway Community Edition 6.0.1 by Boxfuse
Database: jdbc:postgresql://db:5432/app (PostgreSQL 13.0)
WARNING: Flyway upgrade recommended: PostgreSQL 13.0 is newer than this version of Flyway and support has not been tested. The latest supported version of PostgreSQL is 12.
Schema version: 0.002

+-----------+---------+--------------+------+---------------------+---------+
| Category  | Version | Description  | Type | Installed On        | State   |
+-----------+---------+--------------+------+---------------------+---------+
| Versioned | 0.001   | create table | SQL  | 2020-11-11 04:26:21 | Success |
| Versioned | 0.002   | create table | SQL  | 2020-11-11 04:26:21 | Success |
+-----------+---------+--------------+------+---------------------+---------+
```
- Drop all tables
```bash
- docker-compose run --rm flyway clean
```
- Dump database
```bash
- docker-compose exec db pg_dump app -U postgres -s > pg_dump.txt
```
- DB URL
    - localhost:5433
    - user: postgres
    - password: 1234
    - URL: jdbc:postgresql://localhost:5433/postgres