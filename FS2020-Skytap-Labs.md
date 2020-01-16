---
title: FS2020 Lab Instructions for Skytap
toc: false
sidebar: labs_sidebar
folder: master
permalink: /skytaplabs_fs2020.html
summary: api docs
applies_to: [developer,administrator,consumer]
---

# FastStart 2020 Skytap environment user guide
===============

If you plan on using the lab environments hosted on Skytap - you will need to heed these instructions on how to properly start up and shut down/suspend your environment.  You will be reusing this environment over the entire fast start event, shutting down after the last session of the day.

** WARNING ** do not suspend the environment using the suspend feature in skytap, as it is likely your environment will get corrupted.

### Accessing your environment

You instructor will provide you the information to access your environment on Skytap.  

### Start of up the Environment

The Skytap environments will be powered on automatically.  To access the environment click on the `Developer` machine.

Your Credentials for the environment can be found here:
```
user: ibmuser
Password: engageibm
```

When the environment comes up, not all components of CP4I come up automatically.  You will need to run a script.  Here are the instructions:

1. After logging into the developer node using the above credentials, change directories to the `startup-scripts` directory.
2. Run the command `./oc-startup.sh` This will setup your `oc` command line and scale up the event streams and aspera pods.
3. Once complete you can log into the Platform Navigator

### Using the environments

You can access the primary portals for the Cloud Pak here:

Platform Navigator - See shortcut on Web Browser (Chrome)
```
user: admin
password: admin
```

Open Shift Console - See shortcut on Web Browser and/or Platform Navigator
```
user:admin
password: Passw0rd!
```

### One time creation of Shutdown script

Before you can shutdown your environment properly, you will have to create this script somewhere on your developer machine.  To do this follow these steps:

1. Download this file [here](https://github.com/alley28/integration/blob/master/shutdown-cluster.sh) to your Developer machine (in startup-scripts directory or home directory of ibmuser is fine).
2. Perform a `chmod +x shutdown-cluster.sh`

### Shutting down your environment

Before powering off your environment, follow these steps

1. Open Terminal and Enter `su` and type the root password: `IBMDem0s!` (note: this script requires root, thus this step).
2. Run the shutdown script created in the previous section by typing `./shutdown-cluster.sh`
3. It will scale down event streams and aspera and return you back to the prompt once its complete.
4. You can now safely power off the environment.

