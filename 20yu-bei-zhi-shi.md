

## 2.0 预备知识

**什么是镜像（images）？**

镜像是由容器（container）运行的基础。

**基础镜像（base image）、父镜像（parent image）、派生镜像（derivative image）的关系？**

基础镜像的Dockerfile文件中，没有From行，或者有From scratch这一行。

父镜像是作为其它镜像的基础。大多数Dockerfile文件是从父镜像开始，而不是从基础镜像。基础镜像一定是父镜像，但父镜像不一定是基础镜像。派生镜像就是基于基础镜像或者父镜像而制作的镜像。某些时候，基础镜像和父镜像意义是一样的。

