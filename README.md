# containers-for-dealfem
[![](https://img.shields.io/docker/pulls/rrastak/for-dealfem?style=plastic "Docker hub")](https://hub.docker.com/r/rrastak/for-dealfem)
[![For-dealfem](https://github.com/rezarastak/containers-for-dealfem/actions/workflows/ci.yml/badge.svg)](https://github.com/rezarastak/containers-for-dealfem/actions/workflows/ci.yml)

Creates docker containers to compile and run `dealfem`.
In short, these docker containers encapsulate the [deal.II](https://dealii.org) library compiled with additional dependencies [muparser](https://beltoforion.de/en/muparser/), [MPI](https://en.wikipedia.org/wiki/Message_Passing_Interface), and [Trilinos](https://trilinos.github.io).
These images are excellent tools for performing CI and CD in codebases.
You can pull the docker images from the docker hub [repository](https://hub.docker.com/r/rrastak/for-dealfem).
Each container created with these images provides the environment variable `DEAL_II_DIR` which allows `dealfem` code to be compiled properly.

Three different images are provided here:
 * **latest**: The master-branch of `dealii` built using Trilinos that is provided by `ubuntu`.
 * **latest-gcc**: Contains the latest container build using a gcc toolchain.
 * **latest-clang**: The latest latest container using a clang toolchain.
 * **candi**: Master branch of `dealii` built from the [candi](https://github.com/dealii/candi) scripts.

 | Image | Size |
 |---|---|
 |`rrastak/for-dealfem:latest`    | ![](https://img.shields.io/docker/image-size/rrastak/for-dealfem/latest)|
 |`rrastak/for-dealfem:latest-gcc`    | ![](https://img.shields.io/docker/image-size/rrastak/for-dealfem/latest-gcc)|
 |`rrastak/for-dealfem:latest-clang`    | ![](https://img.shields.io/docker/image-size/rrastak/for-dealfem/latest-clang)|
 |`rrastak/for-dealfem:candi`    | ![](https://img.shields.io/docker/image-size/rrastak/for-dealfem/candi)|
