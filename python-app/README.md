# Solution to the assignment

## 1. Create appropriate images for both apps (two separate images!).

Just look at [Dockerfile](./Dockerfile)

### Build the application

<div id="build">

```bash
docker build .
```

</div>


## 2. Launch a container for each created image, making sure, that the app inside the container works correctly and is usable.

```bash
docker run -i -t <ID>
```

Where ID is the ID of the built image (no name is assigned with [this](#build)
command.

## 3. Re-create both containers and assign names to both containers.

1.  First clean up by:
    
    1.  stopping the running container (this python app won't
        have one)

    1.  Remove the stopped container

        ```bash
        docker rm <auto-generated-name>
        ```

1.  Create the container with the name

    <div id="named-run">

    ```bash
    docker run -i -t --name python_test <ID>
    ```

    </div>

## 4. Clean up (remove) all stopped (and running) containers, clean up all created images.

As per 3., stop container and remove it (we can now use the selected name) and
delete the image

```bash
docker rmi <ID>
```

## 5. Re-build the images - this time with names and tags assigned to them.

Like [this](#build) but add `-t python_ass` before the `.` (or the path to the
docker file)

```bash
docker build -t python_ass .
```

## 6. Run new containers based on the re-built images, ensuring that the containers are removed automatically when stopped.

Just like [this](#named-run) but add `--rm` option (remember to first stop and
remove the container if you use the same name as before ;))

```bash
docker run -i -t --name python_test python_ass
```
