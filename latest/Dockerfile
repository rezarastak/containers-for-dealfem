ARG UBUNTU_DOCKER_IMAGE=ubuntu:latest
FROM $UBUNTU_DOCKER_IMAGE
LABEL maintainer="reza.rastak@gmail.com"
RUN apt-get update -q && \
    TZ="America/Los_Angeles" DEBIAN_FRONTEND="noninteractive" apt-get install -y -q \
      build-essential \
      git \
      cmake \
      ninja-build \
      python \
      numdiff \
      libarpack2-dev \
      libboost-iostreams-dev \
      libboost-serialization-dev \
      libboost-system-dev \
      libboost-thread-dev \
      libbz2-dev \
      libgmsh-dev \
      libgsl-dev \
      libhdf5-dev \
      libhdf5-mpi-dev \
      liblapack-dev \
      libmuparser-dev \
      libnetcdf-cxx-legacy-dev \
      libnetcdf-dev \
      libp4est-dev \
      libscalapack-mpi-dev \
      libsuitesparse-dev \
      libsundials-dev \
      libtbb-dev \
      mpi-default-dev \
      trilinos-all-dev \
      zlib1g-dev
ENV DEAL_II_DIR=/opt/dealii
ARG DEAL_II_BUILD_TYPE=Debug
ARG DEAL_II_EXAMPLES=OFF
RUN DEAL_II_SRC=/opt/dealii-src && DEAL_II_BIN=$DEAL_II_SRC/build && \
    git clone https://github.com/dealii/dealii.git $DEAL_II_SRC -b master --depth 1 -q && \
    cmake -GNinja \
      -D DEAL_II_COMPONENT_EXAMPLES=$DEAL_II_EXAMPLES \
      -D CMAKE_BUILD_TYPE=$DEAL_II_BUILD_TYPE \
      -D CMAKE_CXX_STANDARD=17 \
      -D CMAKE_CXX_EXTENSIONS=OFF \
      -D DEAL_II_ALLOW_AUTODETECTION=OFF \
      -D DEAL_II_WITH_MPI=ON \
      -D DEAL_II_WITH_TRILINOS=ON \
      -D DEAL_II_WITH_P4EST=ON \
      -D DEAL_II_WITH_LAPACK=ON \
      -D DEAL_II_WITH_MUPARSER=ON \
      --install-prefix $DEAL_II_DIR -S $DEAL_II_SRC -B $DEAL_II_BIN && \
    cmake --build $DEAL_II_BIN --parallel --verbose && \
    cmake --install $DEAL_II_BIN && \
    rm -rf $DEAL_II_SRC
