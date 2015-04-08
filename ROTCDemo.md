
Gazebo Installation 
===

The ROTC demo requires a special branch of Gazebo. To install, follow the steps below:


1. Clone Gazebo
    
        mkdir ~/code
        cd ~/code
        hg clone gazebo
  
1. Update to the mentor2 demo branch


        hg pull -u
        hg up mentor2_v2


1. Make a build directory

        mkdir build

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


Retrieving Updates:
===

1. Navigate to the gazebo folder, e.g:

        cd ~/code/gazebo/build

1. Download the updates:

        hg up mentor2_v2
        hg pull -u

1. Compile

        make -j 4

1. Install

        sudo make install

    or if you've configured to install locally

        make install