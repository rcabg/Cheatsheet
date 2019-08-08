Cheatsheet
==========

Just a basic cheatsheet for the most common commands/code I use and I tend to forget/get wrong

Contents
---------
**1. [`Tmux`](#Tmux)**  
**2. [`Ubuntu Shell`](#Ubuntu)**  
**3. [`CMake`](#CMake)**  
**4. [`ROS`](#ROS)**  
**5. [`Mercurial`](#Mercurial)**

Tmux
----

```python
tmux                              # creates session
tmux new -s my_cool_name          # creates session with custom name

tmux ls                           # prints available sessions
tmux attach -t my_cool_name       # attaches to session by name
(keys) <Control> + b + d          # detaches from current session

tmux kill-session -t my_cool_name # kills session
```

Ubuntu Shell
------
```python
nmtui                             # graphic network configuration

apt-get install nmap
nmap -sP 192.168.1.0/24           # scans ips on a network

export MY_ENV_VARIABLE=/path/to/somewhere # adds env variable
alias MY_ALIAS='command_to_execute'       # adds alias

df -BG                            # free space in GBs
```

CMake
-----
```cmake
# adds custom env variable to path
if(DEFINED ENV{MY_ENV_VARIABLE})
   set(CMAKE_PREFIX_PATH   ${CMAKE_PREFIX_PATH} $ENV{MY_ENV_VARIABLE})
endif()

# finds package with components (ex: OpenCV)
find_package(OpenCV 3.4 REQUIRED
   COMPONENTS  core highgui imgproc cudawarping cudaobjdetect)
```

ROS
---
```python
# network configuration
export ROS_MASTER_URI=http://MASTER_IP:11311 
export ROS_IP=MY_IP

catkin_make -DCATKIN_BLACKLIST_PACKAGES="pkg1;pkg2" # ignores pkgs to compile
catkin_make -DCATKIN_WHITELIST_PACKAGES="pkg1;pkg2" # compiles only these pkgs
```

Mercurial
---
```python
# enables terminal color (at hgrc file)
[extensions]
color =
```
