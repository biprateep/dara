---
layout: default
title: Storage
nav_order: 6
---

# Storage Space
Dara has a 512GB SSD and a 2TB hard rive which has been divided as follows:
- 60 GB for root (`/`) on the SSD, this is where the OS and all common software installations are installed.
- 406 GB for the home directories of all the users (`/home`) on the SSD
- 1.7 TB on the Hard Drive for data storage (`/data`)   
All the spaces are common to all and no per account limitations are imposed.   
The current status of storage space can be found using the command `df -kh`
Only data that requires fast read and write should be stored in the home directories. Data that requires multiple read-writes should not be stored on the SSDs to increase their lifespan.  

The `/data/common` folder has `rwx` priviledges for everyone. So, store files that you want to share in this directory.
