# load the docker file
    $ docker compose -f docker-compose.ymp up -d

# pull the docker images
    $ docker pull <docker image image>

# check pulled docker images
    $ docker images

# To run the docker images
    $ docker run <docker image name>

# To check the running docker images
    $ docker ps

# To check all the cantainers
    $ docker ps -a

#  To run the docker cantainer
    $ docker --name pythonCamntainer -d python
 Note:  
  --name = it is alias name of the container
  -d = it mean it will run in detaiched mode
  pythonCantainer = it is alias name of the cantainer
  python = it is the docker image name
  python = instead of python we can use images id to run the cantainer

# Run the python image in interactive mode
    $ docker --name pythonContainer1 -it -d python
Note:  
  --name = it is alias name of the container
  -it = it is running in interactive mode
  -d = it mean it will run in detaiched mode
  pythonCantainer = it is alias name of the cantainer
  python = it is the docker image name
  python = instead of python we can use images id to run the cantainer

# To go inside the container
    $ docker exec -it <containerId or image-name> python3
Note:   
  -it = open in interactive mode
  exec = execute the image or cantiainer
  python3 = i want to run python3 version in container

# To check all the information of the container
    $ docker inspect <container-id or running docker image>

