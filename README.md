# radical  

Follow the steps, and type the commands into your terminal, do not type $.  

### 1. Install docker engine
radical docker-image runs on docker, if you have docker engine installed skip this step. This are Linux minimal docker installation guide, if you don't use Linux or you look for a detailed tutorial on Linux/Windows/Mac Docker engine installation please consult [Docker getting Starting] (https://docs.docker.com/linux/step_one/).  

`$ curl -fsSL https://get.docker.com/ | sh `  
*if you don’t have curl search on this document curl installation  
Then type:  
    `$ sudo usermod -aG docker your-user`

###### Important step:  
Log out from your ubuntu session (restart your machine) and get back in into your user session before the next step.
You may need to restart your computer and not just log out from your session in order to changes to take effect.

Test your docker engine with the command:  
`$ docker run hello-world`  

###1 Download radical images from DockerHub
`$ docker pull nselem/radical:latest  `  

#####Important  
`docker pull ` may be slow depending on your internet connection, because nselem/evodivmet docker-image is being downloaded, its only this time won’t happen again.

### 2 Run radical
#### 2.1 Set your partition file  
Create an empty directory that contains your files  
`$ mkdir mydir`  
you can use Example.nxs  
### 2.2 Run your docker nselem/evodivmet image  

`$ docker run -i -t -v /mypath/mydir:/usr/src/radical  nselem/radical /bin/bash`

**/mypath/mydir/** is your local directory were you store your inputs, can have any name you choose.  
Use absolute paths, if you don’t know the path to your dir, place yourself on your directory and type on the terminal  
`$ pwd`  
**/usr/src/radical** is fixed at the docker images, you should always use this name.  


### 2.3 Run radical inside your docker  
`$ run_radical_forked.pl -m Example.nxs -o OUT -c config.ml.example -p 1 `  

once you finished please exit the container  
`$ exit`  
### 2.4 Read your results ! 

This is a docker file of radical http://desalle.amnh.org/software.html  
Using RAXml from https://hub.docker.com/r/cbcrg/raxml-nf/  

