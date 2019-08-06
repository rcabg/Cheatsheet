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

# add env variable
export MY_ENV_VARIABLE=/path/to/somewhere  
```

CMake
-----
```cmake
# Adding custom env variable to path

if(DEFINED ENV{MY_ENV_VARIABLE})
   set(CMAKE_PREFIX_PATH   ${CMAKE_PREFIX_PATH} $ENV{MY_ENV_VARIABLE})
endif()
```

ROS
---
```python
# network configuration
export ROS_MASTER_URI=http://MASTER_IP:11311 
export ROS_IP=MY_IP
```
