# kART-tutorial

This tutorial shows how to use the kinetic Activation-Rexation Technique (kART). 

## Content of the directory

| File | Comment |
| :--- | :--- |
|README.md    | This file |  
|Makefile.vm | Download this file to the Virtual Machine (usr/MAKE) to compile
|Tutorial_new | Input files to run the examples
|Tutorial_results | Fully run examples, useful to compare and validate examples
|kart-master.tar.gz | kART run plus examples

## Documentation

General document for kART can be found here: <https://kart-doc.readthedocs.io/en/latest/user_guide.html>

## Installing the code on the Virtual Machinew

The Virtual Machine contains a kART code ready to be compiled. However, a few things need to be done to compile it:

1. Download the file `Makefile.vm`and put in into the `software/kart_tutorial/src/MAKE` directory.
2. Move to `software/kart_tutorial/src` and compile the code with ` % make vm `
3. Download the `tutorial_new.tar.gz`file and untar it in the `software/kart_tutorial` directory with `% tar xzf tutorial_new.tar.gz`
4. Move into the right directory: `% mv tutorial_new ~/software/kart_master`
5. Install the csh shell : ` % sudo apt-get install csh`



## How to test kART rapidly with "docker"

NOTE: for this installation you need to create a free account on `gitlab.com`.

A `docker` image has also be generated, to be used on Mac, for example, or any machine. 

### Prerequisites
* Install docker (<https://docs.docker.com/compose/install/>)

### Pull an image of kART from gitlab and run examples 

_Depending on how you set up your docker installation, you might need to sudo each command_

Execute the following commands to download an image of kART:
* $ mkdir kart_tutorial; cd kart_tutorial
* $ docker login registry.gitlab.com. [You will need to provide your gitlab username and password]

* $ docker pull registry.gitlab.com/groupe_mousseau/kart:latest

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
