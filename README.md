# Angular-Server docker image
Dockerfile to build angular project and serve using nginx.

Run this command inside the root folder of your angular project

```curl https://raw.githubusercontent.com/jnt0r/angular-server-image/master/Dockerfile | docker build -f - . -t image-name```

To speed up image creation and minimize container size add an `.dockerignore` file. You can copy the example one inside this repository ([file](https://github.com/jnt0r/angular-server-image/blob/master/.dockerignore)).
