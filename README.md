# Angular-Server docker image
Dockerfile to build angular project and serve using nginx.

## Usage

Copy the Dockerfile and past it inside the root of your angular project. Then you can build the image using 

```docker build . -t YOUR_IMAGE_NAME```

To run your container, run 

```docker run YOUR_IMAGE_NAME:latest -d -rm --name YOUR_CONTAINER_NAME```

To speed up image creation and minimize container size add an `.dockerignore` file. You can copy the example one inside this repository ([file](https://github.com/jnt0r/angular-server-image/blob/master/.dockerignore)).

## Other installation options

To automatically get the newest version on build, you can use this command to build your image.

```curl https://raw.githubusercontent.com/jnt0r/angular-server-image/master/Dockerfile | docker build -f - . -t YOUR_IMAGE_NAME```

You then don't need to copy the Dockerfile to your project. The dockerignore file is still usefull then. This command uses the stdin functionality of docker ([docker documentation](https://docs.docker.com/engine/reference/commandline/build/#build-with--)).

## Coming soon / Planned functionality

- Https/ssl (using certbot and let's encrypt)
