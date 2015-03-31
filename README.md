## Creating a Sails.js Development Environment with Vagrant##

These instructions will create a Vagrant virtual machine ready for Sails.js development.
This allows developers to begin writing code without worrying about how to install
or configure Node.js or Sails.js.

### What is Sails.js?

[Check out the explanation in the Sail.js Github repository](https://github.com/balderdashy/sails-docs/blob/master/getting-started/WhatIsSails.md).

###  Install Vagrant ###

- Download and install [VirtualBox 4.3.20](https://www.virtualbox.org/wiki/Download_Old_Builds_4_3)
- Download and install [Vagrant 1.7.1](https://www.vagrantup.com/download-archive/v1.7.1.html) or better

#### Windows Users ####

- Download [Git for Windows](http://msysgit.github.io/):
  - Run the installer and "next" through the wizard until the step to adjust your PATH environment.
  - Choose the third option, "Run Git and included tools from within the Windows Command prompt"
  - **Important**: On the next step, "Configuring the line ending conversions", choose the second option:
    "Checkout as-is, commit Unix-style line endings".
  - Choose "next" through any additional steps to complete the Git for Windows install.
  - Open the Windows Command Prompt as **Administrator**

### Get the Code

[Fork](http://github.com/lynnaloo/sails-vagrant) the `sails-vagrant` repository on Github.

Clone your fork of the `sails-vagrant` repository to a directory on your host machine:

    git clone --recursive https://github.com/<github-username>/sails-vagrant.git

Change directory to your `sails-vagrant` directory:

    cd sails-vagrant

### Setup Vagrant ###

Once you `cd` into the sails-vagrant directory, you will find a "Vagrantfile" which will provide
the necessary instructions and provisioning to setup your development virtual machine. All Vagrant commands
should be performed in this directory with your Vagrantfile.

### Connect to the Virtual Machine ###

Start the virtual machine:

    vagrant up

Connect to the virtual machine via ssh:

    vagrant ssh

- You will find a `dev` folder in the `home/vagrant` directory that will sync all of its contents
  to a `dev` folder adjacent to your Vagrantfile on your host machine. This allows for editing code
  on your host machine and having it immediately available inside of the virtual machine.


## Creating a New Sails Project

Change directory to development:

    cd dev

Create a new app:

    sails new testProject

Now lift the server:

    cd testProject
    sails lift

If you visit (http://localhost:1337/) you will see the default home page. Vagrant will automatically
port-forward localhost:1337 to localhost:1337 on your guest virtual machine.

