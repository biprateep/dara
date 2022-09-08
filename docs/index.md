---
layout: default
title: Home
nav_order: 1
---

Welcome to the Wiki for Dara!  
Here I will try to list down all usage notes for working on Dara. Some of the notes might be useful for you but mostly these notes are aimed for me. Incase something is not working feel free to drop me a mail or text on slack. 

# Accessing Dara
You need to have an account created by Pitt IT. Open a ticket/mail Gracie Gollinger for that. The computer can **only** be accessed via the Pitt Astro VPN, set it up before proceeding.

Once logged into the vpn you can login via the terminal using
```bash
ssh username@dara.phyast.pitt.edu
```

Alternatively you may use the Jupyter hub server via the url : <https://dara.phyast.pitt.edu:8000> and log in using your Pitt user ID and password (the same as dara ssh login). The browser might warn you that the connection is not safe but you can click on the proceed anyway link provided by your browser.


# IMPORTANT PRECAUTIONARY NOTE
**If you are using Tensorflow (or Keras with Tensorflow backend) on Dara:** Please always add the following lines to the beginning of your code. This will prevent Tensorflow from allocating all the memory on the GPUs and make the GPUs unusable for other users. You can check the memory allocation on the GPUs using the command `nvidia-smi` on the terminal as a cross check.   
**For TF 1.X:**

```python
import tensorflow as tf
config = tf.ConfigProto()
config.gpu_options.allow_growth=True
sess = tf.Session(config=config)
```
**For TF 2.X:**
```python
import tensorflow as tf
physical_devices = tf.config.list_physical_devices('GPU')
for device in physical_devices:
    tf.config.experimental.set_memory_growth(device, True)
```
`set_memory_growth` is experimental as of `TF 2.2.0` and might be updated soon.
