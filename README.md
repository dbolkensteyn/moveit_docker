# MoveIt! Docker Images
This repo hosts the :whale: Dockerfiles used to generate images for [MoveIt!](moveit.ros.org):

[![Docker Pulls](https://img.shields.io/docker/pulls/davetcoleman/moveit_docker.svg?maxAge=2592000)](https://hub.docker.com/r/davetcoleman/moveit_docker/)

![Docker Stars](https://img.shields.io/docker/stars/davetcoleman/moveit_docker.svg)](https://registry.hub.docker.com/davetcoleman/moveit_docker/)

[![Compare Images](https://badge.imagelayers.io/davetcoleman/moveit_docker:latest.svg)](https://imagelayers.io/?images=davetcoleman/moveit_docker)

## Usage

    docker run -it davetcoleman/moveit-jade-src

## Build

    docker build -t davetcoleman/moveit_docker:moveit-jade-source .

## Layout

For each distribution there are 3 images, built on top of a standard OSRF image:

 - [osrf/ros:jade-desktop](https://github.com/osrf/docker_images/blob/master/ros/jade/jade-desktop/Dockerfile) ROS Jade Desktop
 - [moveit-jade-source](https://github.com/davetcoleman/moveit_docker/blob/master/jade/source/Dockerfile): contains all installed debian dependencies and all MoveIt! source code downloaded to ~/ws_moveit/src
 - [moveit-jade-build](https://github.com/davetcoleman/moveit_docker/blob/master/jade/build/Dockerfile): built on top of moveit-jade-source, contains a ``catkin build`` version of the same workspace
 - [moveit-jade-release](https://github.com/davetcoleman/moveit_docker/blob/master/jade/release/Dockerfile): the full debian-based install of MoveIt! using apt-get
