Welcome to the Wiki for Dara!  
Here I will try to list down all usage notes, installation notes for maintaining Dara

**NOTE**: The X-window system does not work currently and is being worked on.

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

### Accessing Jupyter via Jupyter-hub
Jupyter hub is in the process of being installed

### Software Installation
Any software installed via `sudo apt-get install <software-name>` should be accessible to all users. Some exceptions might occur (like `conda`) and some additions to the `.bashrc` file might be neccessary. 
