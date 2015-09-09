General Information 
===================

This is a Development Environment for LSF Docker Integration


Directory Structure
===================

| Direcory or File   | Description                                                            |
|--------------------|------------------------------------------------------------------------|
| ./docker           | contains docker projects docker/<project>/                             |
| ./docker/<project> | contains Dockerfile and Dockerenv and all Dockerimage relevat data     |
| ./docker-host      | Vagrant setup for Docker Host - need if host is not able to run docker |
| ./scripts          | Management scripts to start docker images outside vagrant              |
| ./Vagrantfile      | Vagrant setup file - do not modify                                     |

Get Started
===========

1. Place your Dockerproject in the directory ./docker like ./docker/example.
2. Insert a Dockerfile thats describes your docker image
3. Insert a Dockerenv see [link](#-docker-environment)

vagrant up <project>

password: tcuser

ATTENTION: if you chance your Dockerfile or Data inside your Project you need to reload your project with vagrant reload <project> because vagrant dont sync the data to the docker image at the moment

Docker Environment
==================

You can link to other dockerimages or at volumes or forwared ports etc by editing your Dockerenv inside your project (See: http://docs.vagrantup.com/v2/docker/configuration.html)
