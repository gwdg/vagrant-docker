Directory Structure
===================

| Direcory or File     | Description                                                            |
|----------------------|------------------------------------------------------------------------|
| ./docker             | contains docker projects docker/<project>/                             |
| ./docker/\<project\> | contains Dockerfile and Dockerenv and all Dockerimage relevat data     |
| ./docker-host        | Vagrant setup for Docker Host - need if host is not able to run docker |
| ./scripts            | Management scripts to start docker images outside vagrant              |
| ./Vagrantfile        | Vagrant setup file - do not modify                                     |

Get Started
===========

1. Place your Dockerproject in the directory ./docker like ./docker/example.
2. Insert a Dockerfile thats describes your docker image
3. Insert a Dockerenv see [Docker Environment](#docker-environment)

vagrant up example

ATTENTION: if you chance your Dockerfile or Data inside your Project you need to reload your project with vagrant reload \<project\> because vagrant dont sync the data to the docker image at the moment

HINT: You can clone or symlink your project into ./docker directory 

Docker Environment
==================

You can link to other dockerimages or at volumes or forward ports etc by editing your Dockerenv inside your project (See: http://docs.vagrantup.com/v2/docker/configuration.html)

If you want to forward some ports to your host you must also specify this in ./docker-host/Vagrantfile

Docker Debug
==============
You can login into the docker host per vagrant ssh \<docker-host\>. 

1. Search for the docker-host vagrant id with "vagrant global-status"
2. Log into the docker-host "vagrant ssh \<id\>
