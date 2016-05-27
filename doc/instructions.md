## Installation on ubuntu-14.04 64 bit with ros-indigo

To install all the packages on ubuntu 14.04 LTS 64 bit, you should do the following steps:

  1. install ROS-indigo: follow steps 1.1 to 1.3 of [the ROS installation website.](http://wiki.ros.org/indigo/Installation/Ubuntu).

  2. install by apt-get
    - autoconf
    - g++
    - cmake
    - libboost-dev
    - liburdfdom-dev
    - libassimp-dev
    - ros-indigo-xacro
    - ros-indigo-kdl-parser
    - ros-indigo-common-msgs
    - ros-indigo-tf
    - ros-indigo-tf-conversions
    - ros-indigo-libccd
    - ros-indigo-octomap
    - ros-indigo-resource-retriever
    - ros-indigo-urdfdom-py
    - ros-indigo-srdfdom
    - ros-indigo-pr2-robot
    - flex
    - bison
    - asciidoc
    - source-highlight
    - git
    - libomniorb4-dev
    - omniorb-nameserver
    - omniidl
    - omniidl-python
    - libltdl-dev
    - python-matplotlib
    - libtinyxml2-dev
    - liblog4cxx10-dev
    - libltdl-dev
    - qt4-dev-tools
    - libqt4-opengl-dev
    - libqtgui4
    - oxygen-icon-theme

    ```bash
sudo apt-get install autoconf g++ cmake libboost-dev liburdfdom-dev libassimp-dev ros-indigo-xacro ros-indigo-kdl-parser ros-indigo-common-msgs ros-indigo-tf ros-indigo-tf-conversions ros-indigo-libccd ros-indigo-octomap ros-indigo-resource-retriever ros-indigo-srdfdom ros-indigo-pr2-robot flex bison asciidoc source-highlight git libomniorb4-dev omniorb-nameserver omniidl omniidl-python libltdl-dev python-matplotlib libtinyxml2-dev liblog4cxx10-dev libltdl-dev qt4-dev-tools libqt4-opengl-dev libqtgui4 oxygen-icon-theme
    ```

  3. install dependencies of openscenegraph:

    ```bash
sudo apt-get build-dep openscenegraph
    ```

  4. Choose a directory on you file system and define the environment
     variable `DEVEL_DIR` with the full path to this directory.
     - the packages will be cloned into `$DEVEL_DIR/src`,
     - the packages will be installed by default in `$DEVEL_DIR/install`.
     - You may install in another prefix, in that case, you should
       - edit the Makefile downloaded at step 5 and set variable `INSTALL_DIR` accordingly,
       - edit file config.sh downloaded at step 5 and set variable `INSTALL_DIR` accordingly.

  5. Copy Config and Makefile

    ```bash
mkdir -p ${DEVEL_DIR}/src
wget -O $DEVEL_DIR/config.sh https://raw.githubusercontent.com/humanoid-path-planner/hpp-doc/isae/doc/config.sh
wget -O $DEVEL_DIR/src/Makefile https://raw.githubusercontent.com/humanoid-path-planner/hpp-doc/isae/doc/Makefile
    ```

     It is recommanded
       - to set variable `DEVEL_DIR` in your `.bashrc`
       - to source file `config.sh` in your `.bashrc`
     for future use.

  6. cd into `$DEVEL_DIR` and type

    ```bash
cd ${DEVEL_DIR}
source config.sh
    ```

  7. cd into `$DEVEL_DIR/src` and type

    ```bash
cd ${DEVEL_DIR}/src
make all
source ../config.sh;
make hpp_universal_robot.install hpp-environments.install
    ```

##Documentation

  Open `$DEVEL_DIR/install/share/doc/hpp-doc/index.html` in a web brower and you
  will have access to the documentation of most packages.