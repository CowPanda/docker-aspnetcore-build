# docker-aspnetcore-build

# build in command line

```
    docker run --rm -v {your_app_path}:/app -w /app -e SLN_FILE_NAME={your_solution_file_name} -e RELEASE_PATH={publish_path} cowpanda/aspnetcore-build:2.0
```

# build with docker-compose.yml

> docker-compose up -d
> docker-compose down 

```
version: '2'
services:
    aspnetcore-build:
        image: cowpanda/aspnetcore-build:2.0
        container_name: aspnetcore-build-test
        working_dir: /app
        volumes:
            - .:/app
        environment:
            - SLN_FILE_NAME={your_solution_file_name}
            - RELEASE_PATH={your_publish_path}
```

