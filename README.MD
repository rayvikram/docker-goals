## to build docker image
> docker build .

## to start a container 
> docker run -p 3000:3000 <image_id>
- this will create, start container and publish the app in localhost:3000.
- next time if we want to start the app. Just restart the stopped container will work.

> docker run vs docker start

- -p stands for publish 

## NOTES
- Each instructions inside a DockerFile is run by Layer basis
- And they are cached. So next rebuilding of a new Image is faster and it uses the cache.
- All instructions above the CMD is executed inside the image building process and saved.
- CMD is executed while starting the container with the extra commands passed in command line args like -p.
- Containers is just an extra Layer on top of image. 
- So, it uses the code, environment, of the image. IT DOES NOT COPIES THE CODE FROM IMAGE INTO ITS OWN.

## commands
> To View logs
- docker logs -f <c_id>
> -f means follow mode
- docker attach <c_id>
> it will attach to the terminal of the running container
- docker start -a <c_id>
> it will start with attach MODE. NOTE: docker run is detached by default, and docker start id detached mode by default. 
- -i
> Kepp STDIN open even if not attached
- -t
> Opens a PSUDO terminal
- docker run -p 3000:3000 -d --rm <image_id>
> --rm will remove container after it stops
- docker image inspect
- docker cp <source path> <container>:<path>
> to copy to and forth | can be used to copy logs from docker to other location
- --name -> container
- docker build -t <name:tag> .
> name:tag combination is called tag a image
- 

### 