# Installation

## SDFormat

The ROTC demo requires a special branch of SDFormat. To install, follow the steps below:

1. Clone sdformat
    
        mkdir ~/code
        cd ~/code
        hg clone https://bitbucket.org/osrf/sdformat
  
1. Update to the mentor2 demo branch

        cd ~/code/sdformat
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

        cd ~/code/gazebo
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

        cd ~/code/mentor2
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

**NOTE**: The packages should be updated in this order: 1. sdformat, 2. gazebo, 3. mentor2

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

## Source setup file

1. Navigate to the mentor2 directory, e.g.

        cd ~/code/mentor2/

1. Source the environment setup file

        source /usr/local/share/simplegdk/setup.sh

    or if you installed to a local home directory

        source ~/local/share/simplegdk/setup.sh

## Demo worlds

- **gearbox test world**

        gazebo worlds/gearbox_test.world

    1. Expand the joint control widget by dragging on the three white dots on the right border of the gazebo window towards the middle of the screen

    1. click on the motor model in the 3D view to select it and see the joint names appear in the joint control widget.

    1. enter a small number in the `motor_shaft_joint` input field to apply some torque to the motor shaft. The vehicle should start rolling away. Applying large torques may cause the vehicle to be unstable.

    To change the gearbox ratio:

    1. edit the gearbox_test.world file in the `mentor2/worlds` directory

    1. search for the text `gear_ratio`, and change the value

    1. restart gazebo
               

- **region event test world**
               
        ./run.bash worlds/tow.world

    1. Log in by going to `Mentor2` > `Login` menu in the toolbar and entering the URL, username, and password in the dialog.

    1. Expand the joint control widget by dragging on the three white dots on the right border of the gazebo window towards the middle of the screen

    1. click on the car model in the 3D view to select it and see the joint names appear in the joint control widget.

    1. enter a small number in the `chassis_JOINT_1` input field to apply some torque (negative value, e.g. -1.0) to the joint connecting the axle to the chassis. 

    1. Press the play button (first button from the left in the bottom panel). The vehicle should start rolling into the regions in front of it. This triggers events to be posted to the Learning Companion.

    Note: remember to execute `./stop.bash` to kill the server process after exiting the gazebo GUI client


- **Practice world 1 - vehicle_ramp_region world**
               
        ./run.bash worlds/vehicle_ramp_region.world

    1. Log in by going to `Mentor2` > `Login` menu in the toolbar and entering the URL, username, and password in the dialog.

    1. Press the play button to see the vehicle roll down the ramp. This triggers events to be posted to the Learning Companion.

    Note: remember to execute `./stop.bash` to kill the server process after exiting the gazebo GUI client


- **Practice world 2 - vehicle_motor_region world**
               
        ./run.bash worlds/vehicle_motor_region.world

    1. Log in by going to `Mentor2` > `Login` menu in the toolbar and entering the URL, username, and password in the dialog.

    1. Press the play button to see the vehicle roll over the regions in front. This triggers events to be posted to the Learning Companion.

    1. To change the gear ratio: 
        1. Pause the simulation

        1. Right click on the vehicle model in the 3D view and select `Edit model`, 

        1. Double click on the motor box (the casing between the wheels) and change the `gear_ratio` value.

        1. Save the model (`File` > `Save As`) and give it a different name, e.g. `vehicle_2`, and exit the model editor (`File` > `Exit Model Editor`).
 
        1. Press the play button again to see the behavior of the vehicle with the updated gear ratio.

    Note: remember to execute `./stop.bash` to kill the server process after exiting the gazebo GUI client