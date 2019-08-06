Cheatsheet
==========

Just a basic cheatsheet for the most common commands I use.

Contents
---------
**1. [`Tmux`](#Tmux)**  
**2. [`Ubuntu`](#Ubuntu)**  
**3. [`CMake`](#CMake)**  
**4. [`ROS`](#ROS)**

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

Ubuntu
------
```python
nmtui                             # graphic network configuration

apt-get install nmap
nmap -sP 192.168.1.0/24           # scans ips on a network

export MY_ENV_VARIABLE=/path/to/somewhere # add env variable

df -BG                            # free space in GBs
```

CMake
-----
```cmake
# Adds custom env variable to path
if(DEFINED ENV{MY_ENV_VARIABLE})
   set(CMAKE_PREFIX_PATH   ${CMAKE_PREFIX_PATH} $ENV{MY_ENV_VARIABLE})
endif()
```

ROS
---
```python
# Network configuration
export ROS_MASTER_URI=http://MASTER_IP:11311 
export ROS_IP=MY_IP
```
