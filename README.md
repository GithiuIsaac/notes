# notes-app - Docker

Run the notes app using docker and docker-compose

# Set up

Start the docker containers by running

```
docker-compose up -d
```

The app should be viewable on `localhost:5000`. Give time for the docker container with the database to initialize.

Check if the db has initialized by running `docker ps` to check the name of the container running the db. 

Run `docker logs -f <container-name>` to view the logs to see if the db has started.

After the postresql db has started, run 

```
docker-compose run --rm app /bin/sh -c "flask db init && flask db migrate && flask db upgrade"
```

This initializes the db for the flask app. With this you can navigate to `localhost:5000` and you should see the login page.

