# Customizible Docker Buildx Build

# GitHub Action for building and publishing Docker images using [Docker Buildx](https://docs.docker.com/buildx/working-with-buildx/).

# Input Parameters

# docker-build-arg

| Name          | Type      | Default   | Mandatory   |  Description                                                    |
|---------------|-----------|-----------|-------------|-----------------------------------------------------------------|
| tag           | String    |  latest   | No          | Tags (*comma separated*) to apply to the image                  |
| imageName     | String    |           | Yes         | Name of the image                                               |
| dockerFile    | String    |Dockerfile | No          | Name of the Dockerfile                                          |
| buildArg      | String    |  none     | No          | Docker build --build-arg  flags (*comma separated*)             |
| publish       | Boolean   |  false    | No          | Indicate if the builded image should be published on Docker HUB |
| platform      | String    |  linux/amd64,linux/arm64,linux/arm/v7   | No         | Platforms (*comma separated*) that should be used to build the image |                 |
| dockerHubUser |  String   | Only if  publish  is true | User that will publish the image                      |
| dockerHubPassword| String |         | Only if  publish is true         | Password of the  dockerHubUser               |

| Name                | Type    | Default                                | Mandatory                 | Description                                                          |
| ------------------- | ------- | -------------------------------------- | ------------------------- | -------------------------------------------------------------------- |
| `tag`               | String  | `latest`                               | No                        | Tags (*comma separated*) to apply to the image                       |
| `imageName`         | String  |                                        | Yes                       | Name of the image                                                    |
| `dockerFile`        | String  | `Dockerfile`                           | No                        | Name of the Dockerfile                                               |
| `buildArg`          | String  | `none`                                 | No                        | Docker build `--build-arg` flags (*comma separated*)                 |
| `publish`           | Boolean | `false`                                | No                        | Indicate if the builded image should be published on Docker HUB      |
| `platform`          | String  | `linux/amd64,linux/arm64,linux/arm/v7` | No                        | Platforms (*comma separated*) that should be used to build the image |  |
| `dockerHubUser`     | String  |                                        | Only if  publish is true | User that will publish the image                                     |
| `dockerHubPassword` | String  |                                        | Only if  publish is true | Password of the `dockerHubUser`                                      |
## master

 ## Example

 -yaml
  name: docker-buildx-push
{
 on:
  push:
    branches: 
    
### master
}
  jobs:
  docker -buildx:
    runs-on: ubuntu-latest
    steps: 
{
       name: Checkout master
        uses: actions/checkout@master
}
        name: Build and publish image
        uses: zmingxie/docker_buildx@master
        with:
        
{         publish: true
          imageName: YOUR_IMAGE_NAME_HERE <massto>
          dockerHubUser: YOUR_USER_HERE  <massto>
          dockerHubPassword: YOUR_PASSWORD_HERE <Masoud****9>

}

