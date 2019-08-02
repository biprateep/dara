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

### Account creation, settings and priviledges for different accounts
Accounts now use Pitt's, single sign on solution and hence need to be processed through Gracie.  
The account priviledges can be changed by any of the admins/sudo-ers. Add the usernames to the `/etc/group` file. For ex:
```bash
sudo vim /etc/group
```
and then add the username `xyz123` to the `adm` and `sudo` list.

### Accessing jupyter via Jupyter hub
Jupyter hub is in the process of being installed

### Software Installation
Any software installed via `sudo apt-get install <software-name>` should be accessible to all users. Some exceptions might occur (like `conda`) and some additions to the `.bashrc` file might be neccessary. 
