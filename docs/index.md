Welcome to the Wiki for Dara!  
Here I will try to list down all usage notes, installation notes for maintaining Dara1

### Setting up Conda

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
