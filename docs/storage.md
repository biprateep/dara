---
layout: default
title: Storage
nav_order: 6
---

# Storage Space
Dara has a 512GB SSD, a 2TB hard drive and a 10TB hard drive drive which has been divided as follows:
- 60 GB for root (`/`) on the SSD, where the OS and all common software are installed.
- 406 GB for the home directories of all the users (`/home`) on the SSD
- 1.7 TB on Hard Drive for data storage (`/data`)
- 9.1 TB on Hard Drive for data storage (`data2`)
All the spaces are common to all and no per account limitations are imposed.   
The current status of storage space can be found using the command `df -kh`
Only data that requires fast read and write should be stored in the home directories. Data that requires multiple read-writes should not be stored on the SSDs to increase their lifespan.  

The `/data/common` folder has `rwx` priviledges for everyone. So, store files that you want to share in this directory.

Private directories are not automatically created on the hard drives for every user. To create a directory for `user123` follow these steps, once you are in one of the data directories:
1. `mkdir user123`
2. `sudo chown -R user123 user123`
3. `sudo chgrp -R user123 user123`
