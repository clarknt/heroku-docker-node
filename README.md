# heroku-docker-node
Sample setup for publishing a Node.js app on Heroku within a Docker container. 

Adapted from these official sources:
- [Dockerizing a Node.js web app](https://nodejs.org/en/docs/guides/nodejs-docker-webapp/)
- [Container Registry & Runtime (Docker Deploys)](https://devcenter.heroku.com/articles/container-registry-and-runtime)

## Local launch

### Build
```sh
$ docker build -t heroku-docker-node .
```

### Run
```sh
$ docker run -p 8080:8080 -e PORT=8080 -d heroku-docker-node
```

### Test
```sh
$ curl -i localhost:8080
```

## Heroku launch

### Create
```sh
$ heroku container:login
$ heroku create
```

### Push/release
```sh
$ heroku container:push web
$ heroku container:release web
```

### Test
```sh
$ heroku open
```