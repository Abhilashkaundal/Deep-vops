# Deep-vops
### Step1-: pull & check images
~~~
docker pull  {image_name}
docker images 
docker images --all
~~~

### Step2-: run the images
~~~
docker run -it {image_name}
#volume mount 
docker run -it -v {path of volume} {image_name}
#detached mode and  passing the gpus for index number
docker run -it -d  -v {path of volume} --gpus "device=0" {image_name}
#passing the port and name 
docker run -it -d -v {path of volume} --gpus "device=0" -p {passing the port} --name {enter the name} {image_name}
~~~
