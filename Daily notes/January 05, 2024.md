This week I have been working full time on [[Visio]] and now that the small and easy stuff are all pretty much done it is time to move to the more complex stuff that I have never worked on.
Today I am implementing **[[Internet Protocol#IP Address| IP address]] based [[Rate Limiting| rate limiting]]** for the `/api` endpoints.


It is now 9 PM and I haven't had the time to work on the rate limiting.

### What I worked on today
- Integration tests
- Docker and docker compose

### What I learned today
#### Go test behavior
While running `go test` directly on a test file it only takes that file into context, so even if there is another file in the same package with some exported stuff it won't be able to find it. 
#### Docker compose and .env files
You can use environment files in a `docker-compose.yml` file because [[Docker#Compose | docker compose]] reads all .env files in the current directory. We can then use them in our [[Docker#Dockerfile | Dockerfile]] or docker-compose.yml like this
```yml
    container_name: server
    volumes:
      - ${CODE_DIR}:/go/src/app 
    depends_on:
      - postgres

```

```.env
CODE_DIR="/some/path"
```