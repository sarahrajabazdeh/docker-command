# docker-command
my cheetsheet docker command
# image list 
sudo docker images
# container list 
sudo docker ps -a
# run an image 
docekr run image_name 
this command chek if you have image_name image in your local computer run it and if not, try to pull it from docker hub and then run it 
# ls of image 
docker run image_name ls /
# remove all container 
sudo docker rm -f $(sudo docker ps -aq)
# container id 
docker run -d image_name 
# stop container after run it 
docker run --rm image_name
#specify a name for container
docker run --name sara image_name 
# to see low level information about container
docker run -d image_name 
and then :
docker run inspect (output of previous command) 
it contains info like: network settings and log path .enjoy it :)
# port number
-it gives u to work(change, update) with that image 
-p hostport : container port 
docker run -it -p 8000:80 image_name
# docker logs command
docker logs container-id
# detect image layer 
docker history imgage_name
### every change you've made via run , create a new layer 
# build a docker image 
docker build -t image_name .
after it built, run it using output previous command 
docker run -it (privious output)

# tips
 -chian RUN instructions in dockerfile to limit layer.
 -if u want to change dockerfile ,dont forget to build it to apply those changes.
 -ADD command can copy or if its not exist , download it then copy it or have ability to unpack compressed file.generally COPY is prefered . just need ADD when you know you need it. COPY is more transparent and use when you want to copy your local repo into container.
 
# build a dockerimage using port
docker run -d -p 5000:5000 imageid

# working with container interactively
docker exec -it container_id (a command which you want to run in container)

# all the running processes in this container
ps axu
# how to link between two container
docker run -d -p 5000:5000 --link
# container IP 
docker inspect container_id | grep IP

# list all docker networks 
docker network ls
i should mension that when docker initialized, docker deamon create docker network bridge by default. to get more information type:
docker network inspect bridge 
# to see ifconfig a container
docker exec -it container_name ifconfig


