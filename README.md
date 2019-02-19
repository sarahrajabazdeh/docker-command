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
