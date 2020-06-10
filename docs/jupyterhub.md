---
layout: default
title: Jupyter-Hub
nav_order: 4
---

# Launching a Jupyter-Hub Server (The method should be updated in future in favor of something more robust)   

If the Jupyter-Hub server is not running you can start an instance yourself by logging in to dara via ssh. First type `tmux` on the terminal which should open a dummy terminal which can be run on the background. Move to the directory `/opt/jupyterHub` and then type `jupyterhub` this should start a Jupyter-Hub server if not already running. You can press `ctrl + b` and then `d` to get out of the tmux terminal and close your terminal to let the process run in the background.

# Accessing Jupyter via Jupyter-Hub
Jupyter-Hub is in principle installed on Dara. It does not work as a full time service and may not be available sometimes but can always be started by the user if it is not available.    
After passing through the Pitt VPN go to the url : <https://dara.phyast.pitt.edu:8000> and log in using your Pitt user ID and password (the same as dara ssh login). The browser might warn you that the connection is not safe but you can click on the proceed anyway link provided by your browser.   

### Interactive `matplotlib`
please run the following in a cell or the terminal to have interactive matplotlib within jupyter-hub.
```python
%matplotlib widget
```

# Installation recipe for Jupyter Hub
