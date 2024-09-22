---
date: 2024-05-04T14:19
tags:
  - Docker
  - Postgres
---
```
> docker pull postgres:15.6
> docker images
> docker run --name pg-15.6 -p 5432(5433, 5434):5432 -e POSTGRES_USER=myuser -e POSTGRES_PASSWORD=123 -e POSTGRES_DB=pgdb -d postgres:15.6
> docker ps -a
> docker exec -it pg-15.6 /bin/bash
> psql -U myuser pgdb

```

