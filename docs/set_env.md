---
layout: default
title: Setting up your account
nav_order: 2
---

# Account creation, settings and privileges for different accounts
Accounts now use Pitt's, single sign on solution and hence need to be processed through Gracie.  
The account priviledges can be changed by any of the admins/sudo-ers. Add the usernames to the `/etc/group` file. For ex:
```bash
sudo vim /etc/group
```
and then add the username `xyz123` to the `adm` and `sudo` list.


# Setting up Conda for your account

Conda should already be installed for all users. You can SSH into Dara using your Pitt username and password. Be sure to either be connected to the University LAN or via the **Physics and Astronomy** VPN.  
Add the following code snippet to your local `.bashrc` file.   

```bash
# >>> conda initialize >>>
# !! Contents within this block are managed by 'conda init' !!
__conda_setup="$('/home/miniconda3/bin/conda' 'shell.bash' 'hook' 2> /dev/null)"
if [ $? -eq 0 ]; then
    eval "$__conda_setup"
else
    if [ -f "/home/miniconda3/etc/profile.d/conda.sh" ]; then
        . "/home/miniconda3/etc/profile.d/conda.sh"
    else
        export PATH="/home/miniconda3/bin:$PATH"
    fi
fi
unset __conda_setup
# <<< conda initialize <<<
```

# Paths for Astro softwares

# Paths for GPU drivers
