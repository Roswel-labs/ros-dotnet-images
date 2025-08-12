# ros-dotnet-images

ROS .NET Docker images.

## Images

Accessible at [Docker Hub](https://hub.docker.com/r/fxxholub/ros2-dotnet).

All images are based on Ubuntu and [ROS Open Container Initiative Images](https://github.com/sloretz/ros_oci_images/tree/main).

### Dotnet 8.0
| ROS variant     | amd64 | arm/v7 | arm64/v8 |
|-----------------|-------|--------|----------|
| [ROS Humble](http://docs.ros.org/en/humble) |
| ros-core        | ✅     | ❌      | ✅      |
| ros-base        | ✅     | ❌      | ✅      |
| desktop         | ❌     | ❌      | ❌      |
| perception      | ❌     | ❌      | ❌      |
| simulation      | ❌     | ❌      | ❌      |
| desktop-full    | ❌     | ❌      | ❌      |

## Building

### Automatic

Runs at 00:00 UTC on the 1st of every month, using GitHub actions. Images are pushed to the Docker Hub

### Manual

- create multiplatform builder

`docker buildx create --platform linux/amd64,linux/arm/v8`

- use multiplatform builder

`docker buildx use <builder_name>`

- set DOCKER_HUB_USERNAME

`DOCKER_HUB_USERNAME=<your_docker_username>`

- build

```
docker buildx build \
    --platform linux/amd64,linux/arm64/v8 \
    -t $DOCKER_HUB_USERNAME/ros2-dotnet:humble-core-8.0-runtime \
    --push .
```
