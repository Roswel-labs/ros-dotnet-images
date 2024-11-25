# ros-dotnet-images

ROS .NET Docker images.

## About the images

All images are Ubuntu based.

Images are based on [ROS Open Container Initiative Images](https://github.com/sloretz/ros_oci_images/tree/main).

| Image           | amd64 | arm v7 | arm64 v8 | Full Image Name                            |
|-----------------|-------|--------|----------|--------------------------------------------|
| [ROS Humble](http://docs.ros.org/en/humble)                                                 |
| ros-core        | ❌     | ❌      | ❌        | ``      |
| ros-base        | ✅     | ❌      | ✅        | `TODO`      |
| desktop         | ❌     | ❌      | ❌        | `-`       |
| perception      | ❌     | ❌      | ❌        | `-`    |
| simulation      | ❌     | ❌      | ❌        | `-`    |
| desktop-full    | ❌     | ❌      | ❌        | `-`  |


## How to build

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
    -t $DOCKER_HUB_USERNAME/ros2-dotnet:humble-8.0 \
    --push .
```
