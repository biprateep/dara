---
layout: default
title: Jupyter-Hub
nav_order: 4
---
# Jupyter-Hub

## Launching a Jupyter-Hub Server  
The Jupyter hub server runs as a service on Dara and should be available whenever the machine is on. "[The Littlest Jupyterhub](https://tljh.jupyter.org/en/latest/index.html)" is the specific distribution installed on Dara.  




## Accessing Jupyter via Jupyter-Hub
    
After passing through the Pitt VPN go to the url : <https://dara.phyast.pitt.edu:8000> and log in using your Pitt user ID and password (the same as dara ssh login). The browser might warn you that the connection is not safe but you can click on the proceed anyway link provided by your browser. Jupyterhub runs as a service and starts automatically when the machine is switched on.    

### Interactive `matplotlib`
please run the following in a cell or the terminal to have interactive matplotlib within jupyter-hub.
```python
%matplotlib widget
```

## Installation recipe for Jupyter Hub

"The Littlest JupyterHub" is the distribution installed on Dara. Initial installation followed these steps:
1. Install the software following instructions here: <https://tljh.jupyter.org/en/latest/install/custom-server.html>
2. Check logs via instructions here to perform troubleshooting: <https://tljh.jupyter.org/en/latest/troubleshooting/logs.html>
3. There was an error about module `jupyter_core` not found. Fixed that with the following command:
   ```bash
   sudo /opt/tljh/user/bin/python3 -m pip install jupyter
   ```
5. Update the config file following these instructions: <https://tljh.jupyter.org/en/latest/topic/tljh-config.html> to set the following attributes. They make the server available at the right url and port.
```yaml
users:
  admin:
  - bid13
http:
  port: 8000
  address: dara.phyast.pitt.edu

```
6. The default for the distribution is to create new home directories for jupyter users which are separate from the system ones. Employed the following fix to have the same directories available: <Have to fix teh issue with tljh creating new useraccounts instead of the system ones. 
use this patch: https://github.com/jupyterhub/the-littlest-jupyterhub/issues/705#issuecomment-1070827940>
