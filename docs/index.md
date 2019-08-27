Welcome to the Wiki for Dara!  
Here I will try to list down all usage notes, installation notes for maintaining Dara

### Setting up Conda for your account

Conda should already be installed for all users. You can SSH into Dara using your Pitt username and password. Be sure to either be connected to the University LAN or via the **Physics and Astronomy** VPN.  
Add the following code snippet to your local `.bashrc` file.   

```bash
# >>> conda initialize >>>
# !! Contents within this block are managed by 'conda init' !!
__conda_setup="$('/opt/anaconda3/bin/conda' 'shell.bash' 'hook' 2> /dev/null)"
if [ $? -eq 0 ]; then
    eval "$__conda_setup"
else
    if [ -f "/opt/anaconda3/etc/profile.d/conda.sh" ]; then
        . "/opt/anaconda3/etc/profile.d/conda.sh"
    else
        export PATH="/opt/anaconda3/bin:$PATH"
    fi
fi
unset __conda_setup
# <<< conda initialize <<<
```

Most basic packages that we need are already installed. If some additional package needs to be installed, please use:  
```bash
conda install --user <package-name>
```
or  
```bash
pip install --user <package-name>
```
The conda based installation should be favoured.
### Storage Space
Dara has a 512GB SSD and a 2TB hard rive which has been divided as follows:
- 60 GB for root (`/`) on the SSD, this is where the OS and all common software installations are installed.
- 406 GB for the home directories of all the users (`/home`) on the SSD
- 1.7 TB on the Hard Drive for data storage (`/data`)   
All the spaces are common to all and no per account limitations are imposed.   
The current status of storage space can be found using the command `df -kh`
Only data that requires fast read and write should be stored in the home directories. Data that requires multiple read-writes should not be stored on the SSDs to increase their lifespan.

### Account creation, settings and priviledges for different accounts
Accounts now use Pitt's, single sign on solution and hence need to be processed through Gracie.  
The account priviledges can be changed by any of the admins/sudo-ers. Add the usernames to the `/etc/group` file. For ex:
```bash
sudo vim /etc/group
```
and then add the username `xyz123` to the `adm` and `sudo` list.

### Accessing Jupyter via Jupyter-Hub
Jupyter-Hub is in principle installed on Dara. It does not work as a full time service and may not be available sometimes but can always be started by the user if it is not available.    
After passing through the Pitt VPN go to the url : <https://dara.phyast.pitt.edu:8000> and log in using your Pitt user ID and password (the same as dara ssh login). The browser might warn you that the connection is not safe but you can click on the proceed anyway link provided by your browser.   

**IMPORTANT PRECAUTIONARY NOTE**  
If you are using Tensorflow on Dara Please add the following lines to your code. This will prevent Tensorflow to allocate all the memory on the GPU and make the GPUs unusable for other users. You can check the memory allocation on the GPUs using the command `nvidia-smi` on the terminal as a cross check.

```python
config = tf.ConfigProto()
config.gpu_options.allow_growth=True
sess = tf.Session(config=config)
```

**Launching a Jupyter-Hub Server** (The method will be updated in the future in favor of something more robust)   

If the Jupyter-Hub server is not running you can start an instance yourself by logging in to dara via ssh. First type `screen` on the terminal which should open a dummy terminal which can be run on the background. Move to the directory `/opt/jupyterHub` and then type `jupyterhub` this should start a Jupyter-Hub server if not already running. You can press `ctrl + a` and then `ctrl + d` to get out of the screened terminal and close your terminal to let the process run in the background.

### Software Installation
Any software installed via `sudo apt-get install <software-name>` should be accessible to all users. Some exceptions might occur (like `conda`) and some additions to the `.bashrc` file might be neccessary. 
