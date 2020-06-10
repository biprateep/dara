---
layout: default
title: Softwares and Python packages
nav_order: 3
---

# Software Installation
Any software installed via `sudo apt-get install <software-name>` should be accessible to all users. Some exceptions might occur (like `conda`) and some additions to the `.bashrc` file might be neccessary. Please drop me a text if you need to install any software which require `sudo` priviledges.

# Python Packages
Most basic packages that we need are already installed. If some additional package needs to be installed, please use:  
```bash
conda install --user <package-name>
```
or  
```bash
pip install --user <package-name>
```
The conda based installation should be favoured.

# Recipe for conda virtual environments
- To make the environments available to everyone login as root: `sudo bash`
- 
