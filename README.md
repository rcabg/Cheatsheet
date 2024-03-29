Cheatsheet
==========

Just a basic cheatsheet for the most common commands/code I use and I tend to forget/get wrong

Contents
---------
**1. [`Git`](#Git)**  
**2. [`Mercurial`](#Mercurial)**  
**3. [`ROS`](#ROS)**  
**4. [`Ubuntu Shell`](#Ubuntu)**  
**5. [`CMake`](#CMake)**  
**6. [`Tmux`](#Tmux)**  
**7. [`Virtualenv`](#Virtualenv)**


Git
---
```bash
git reset --hard COMMIT_HASH           # discards local changes (without saving them)
git reset --keep COMMIT_HASH           # discards local changes (saving them)
git reset --soft HEAD~1                # discards last commit
git checkout HEAD path/to/file.ext     # restores file to its last commited version

git stash                              # saves local changes
git stash -u                           # saves local changes (including untracked files)
git stash -a                           # saves local changes (including untracked and ignored files)
git stash pop                          # applies stashed files (removing them from stash)
git stash apply                        # applies stashed files (keeping them from stash)
git stash clear                        # removing stash

git checkout -b BRANCH                 # creates new branch and moves to it
git push -u origin BRANCH              # pushes branch for the first time
git branch -d BRANCH                   # deletes branch
git push origin --delete OTHER_BRANCH  # deletes remote branch 

git merge OTHER_BRANCH                 # merges OTHER_BRANCH to current one
git mergetool                          # uses default merge tool for conflicts
```

Mercurial
---
```bash
# enables terminal color (at hgrc file)
[extensions]
color =
```

ROS
---
```bash
# network configuration
export ROS_MASTER_URI=http://MASTER_IP:11311 
export ROS_IP=MY_IP

catkin_make -DCATKIN_BLACKLIST_PACKAGES="pkg1;pkg2" # ignores pkgs to compile
catkin_make -DCATKIN_WHITELIST_PACKAGES="pkg1;pkg2" # compiles only these pkgs
```

Ubuntu Shell
------
```bash
nmtui                             # graphic network configuration

apt-get install nmap
nmap -sP 192.168.1.0/24           # scans ips in a network

export MY_ENV_VARIABLE=/path/to/somewhere # adds env variable
alias MY_ALIAS='command_to_execute'       # adds alias

df -BG                            # free space in GBs

ls | grep "filter_text"           # shows list of files containing filter_text

lscpu                             # info about CPU (cores, architecture...)
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

Tmux
----

```bash
tmux                              # creates session
tmux new -s my_cool_name          # creates session with custom name

tmux ls                           # prints available sessions
tmux attach -t my_cool_name       # attaches to session by name
(keys) <Control> + b + d          # detaches from current session

tmux kill-session -t my_cool_name # kills session
```

Virtualenv
----------

```bash
virtualenv NAME --python=python3 # creates virtual environment for python3

activate NAME                    # opens virtual environment
deactivate                       # closes virtual environment
```