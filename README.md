# ROS2-install-guide

# Reference 

Official Guide https://index.ros.org/doc/ros2/Installation/Dashing/Linux-Install-Debians/
표윤석박사님 at https://cafe.naver.com/openrt/23846 
pinkwink at https://pinkwink.kr/1284


# Install 

## step 1. Setup Locale¶

    sudo locale-gen en_US en_US.UTF-8
    sudo update-locale LC_ALL=en_US.UTF-8 LANG=en_US.UTF-8
    export LANG=en_US.UTF-8

## step 2. Setup Sources¶

    sudo apt update && sudo apt install curl gnupg2 lsb-release
    curl -s https://raw.githubusercontent.com/ros/rosdistro/master/ros.asc | sudo apt-key add -
    
    sudo sh -c 'echo "deb [arch=$(dpkg --print-architecture)] http://packages.ros.org/ros2/ubuntu $(lsb_release -cs) main" > /etc/apt/sources.list.d/ros2-latest.list'

    
## step 3. Install ROS 2 packages¶

### requirement 

    sudo apt install -y \
      build-essential \
      cmake \
      curl \
      gimp \
      git \
      gnupg2 \
      gparted \
      htop \
      iftop \
      iperf \
      kdenlive \
      kolourpaint \
      lsb-release \
      mc \
      ntpdate \
      okular \
      qtcreator \
      shutter \
      simplescreenrecorder \
      terminator \
      tig \
      tmux \
      vim \
      vlc \
      wget \
      xclip
      
### install 

    sudo apt update
    sudo apt install ros-dashing-desktop


    #if you do not need GUI tools
    sudo apt install ros-dashing-ros-base
    
    
## step 4. env setting

    source /opt/ros/dashing/setup.bash

    sudo apt install -y python3-pip
    pip3 install -U argcomplete


## install test

    ros2 run demo_nodes_cpp talker
    ros2 run demo_nodes_py listener


## Uninstall

    sudo apt remove ros-dashing-* && sudo apt autoremove
