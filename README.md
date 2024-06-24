# kART-tutorial

This tutorial shows how to use the kinetic Activation-Rexation Technique (kART). 

## Content of the directory

| File | Comment |
| :--- | :--- |
|README.md    | This file |  
|Makefile.vm | Download this file to the Virtual Machine (usr/MAKE) to compile
|Tutorial_new | Input files to run the examples
|Tutorial_results | Fully run examples
|kart-master.tar.gz | kART run plus examples

## Documentation

General document for kART can be found here: <https://kart-doc.readthedocs.io/en/latest/user_guide.html>

## Installing the code

The Virtual Machin contains a kART code ready to be compiled to compile it:

1. Download the file `Makefile.vm`and put in into the `software/kart_tutorial/src/MAKE` directory.


# How to test kART rapidly with "docker"

## Prerequisites
* Install docker (<https://docs.docker.com/compose/install/>)

## Pull an image of kART from gitlab and run examples 

_Depending on how you set up your docker installation, you might need to sudo each command_

Execute the following commands to download an image of kART:
* $ cd kart_dir  (might be optional)
* $ docker login registry.gitlab.com. [You will need to provide username and password]

* $ docker pull registry.gitlab.com/groupe_mousseau/kart:latest

You can now see the image in the list of docker images:
* $ docker images

To run kART, for instance on the Si-vac-lammps example:
* $ docker run -it registry.gitlab.com/groupe_mousseau/kart:latest
* $ cd kART-tutorials/Si-vac-lammps
* $ mpirun -np 4 ./KMC.sh 

If that does not work (unlikely) try: 
* $ ./KMC.sh

Explore the files printed in the opened session; created files will be deleted at exit.

To exit:
* $ exit
* $ docker logout registry.gitlab.com


## To build an image of kART, locally
* $ cd kart_dir
* $ docker build -t registry.gitlab.com/groupe_mousseau/image_name:image_tag .
* $ docker images (to check that docker list has been updated)

## To build an image of kART, and push it on gitlab container registry
* Follow instructions given on the following page: https://gitlab.com/groupe_mousseau/kart/container_registry
