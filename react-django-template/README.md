# Build Steps

The zip consists of two folder. **frontend** and **backend**.

- frontend consists of react application.
- backend contains django application.

## How to run/build

Everything is there to get started. So if all you want is to run and test.

- Open CMD in the folder(where docker-compose.yml is located)
- To run
  - type `docker-compose -f docker-compose.yml -f docker-compose-dev.yml> up` to run in **development** mode.
  - type `docker-compose -f docker-compose.yml -f docker-compose-prod.yml> up` to run in **production** mode.
- Now you can go to your browser and search `localhost:3000` for **react** and `localhost:8000` for **django**.
- Once you find test everything and are satisfied. You can tear everything down with the same command but with `down` instead of `up` like
  `docker-compose -f docker-compose.yml -f docker-compose-dev.yml>`**`down`**
  similarly for prod run.
  `docker-compose -f docker-compose.yml -f docker-compose-prod.yml>`**`down`**

> Note - Your terminal will be blocked after typing command. So if want non-blocking terminal add `-d` to the command.  
> `docker-compose -f docker-compose.yml -f docker-compose-prod.yml> up`**`-d`**
