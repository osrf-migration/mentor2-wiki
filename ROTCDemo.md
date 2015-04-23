# Installation

## SDFormat

The ROTC demo requires a special branch of SDFormat. To install, follow the steps below:

1. Clone sdformat
    
        mkdir ~/code
        cd ~/code
        hg clone https://bitbucket.org/osrf/sdformat
  
1. Update to the mentor2 demo branch


        hg pull -u
        hg up mentor2_v2


1. Make a build directory

        mkdir build
        cd build

1. Run CMake

        cmake ..

    or install to a local home directory

        cmake -DCMAKE_INSTALL_PREFIX=$HOME/local

1. Compile

        make -j 4

1. Install

        sudo make install

    or if you've configured to install locally

        make install


## Gazebo 

The ROTC demo requires a special branch of Gazebo. To install, follow the steps below:


1. Clone Gazebo
    
        mkdir ~/code
        cd ~/code
        hg clone https://bitbucket.org/osrf/gazebo
  
1. Update to the mentor2 demo branch


        hg pull -u
        hg up mentor2_v2


1. Make a build directory

        mkdir build
        cd build

1. Run CMake

        cmake ..

    or install to a local home directory

        cmake -DCMAKE_INSTALL_PREFIX=$HOME/local

 
1. Compile

        make -j 4

1. Install

        sudo make install

    or if you've configured to install locally

        make install

## MENTOR2

The ROTC demo requires a special branch of MENTOR2. To install, follow the steps below:


1. Clone mentor2
    
        mkdir ~/code
        cd ~/code
        hg clone https://bitbucket.org/osrf/mentor2
  
1. Update to the v2 demo branch

        hg pull -u
        hg up v2


1. Make a build directory

        mkdir build
        cd build

1. Run CMake
 
        cmake ..

    or install to a local home directory

        cmake -DCMAKE_INSTALL_PREFIX=$HOME/local

1. Compile

        make -j 4

1. Install

        sudo make install

    or if you've configured to install locally

        make install


## Retrieving Updates


1. Navigate to the source directory of the sdformat/gazebo/mentor2 packages, e.g.

        cd ~/code/gazebo/build

1. Download the updates:

        # NOTE! In the case of the mentor2 package: hg up v2        
        hg up mentor2_v2
        hg pull -u

1. Compile

        make -j 4

1. Install

        sudo make install

    or if you've configured to install locally

        make install

# Running M2 Demos

1. source the environment setup file

        source /usr/local/share/simplegdk/setup.sh

    or if you installed to a local home directory

        source ~/local/share/simplegdk/setup.sh

1. Run a demo world, e.g.

        gazebo demo.world
