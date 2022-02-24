# notes-app

Demo on how to run the notes app using docker and docker-compose

# Set up

To run the project, start the docker containers by running

```
docker-compose up -d
```

The project should be viewable on `localhost:5000`. Give time for the docker container with the database to initialize.

You can check if the db has initialized by running `docker ps` to check the name of the container running the db. 

Then run `docker logs <container-name>` to check the logs to see if the db has started.

After the postresql db has started, you can then run 

```
docker-compose run --rm app /bin/sh -c "flask db init && flask db migrate && flask db upgrade"
```

This initializes the db for the flask app. With this you can navigate to `localhost:5000` and you should see the login page.

