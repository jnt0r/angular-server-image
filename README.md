# Angular-Server docker image
Dockerfile to build angular project and serve using nginx.

## Usage

Copy the Dockerfile you want to use and past it inside the root of your angular project. Then you can build the image using 

```docker build . --rm -t YOUR_IMAGE_NAME```

To run your container, run 

```docker run -d --rm -p 80:80 -p 443:443 --name YOUR_CONTAINER_NAME YOUR_IMAGE_NAME```

To speed up image creation and minimize container size add an `.dockerignore` file. You can copy the example one inside this repository ([file](https://github.com/jnt0r/angular-server-image/blob/master/.dockerignore)).

# Dockerfile options

There are two Dockerfiles in this repository. The `Dockerfile` creates nginx server without ssl enabled. The `Dockerfile.localhost` creates a DEVELOPMENT server with an ssl certificate for localhost. To use this Dockerfile with the certificate you also need the `localhost-ssl.conf` inside the root of your project.

## Other installation options

To automatically get the newest version on build, you can use this command to build your image.

```curl https://raw.githubusercontent.com/jnt0r/angular-server-image/master/Dockerfile | docker build -f - . -t YOUR_IMAGE_NAME```

You then don't need to copy the Dockerfile to your project. The dockerignore file is still usefull then. This command uses the stdin functionality of docker ([docker documentation](https://docs.docker.com/engine/reference/commandline/build/#build-with--)).

## Coming soon / Planned functionality

- Https/ssl (using certbot and let's encrypt)
