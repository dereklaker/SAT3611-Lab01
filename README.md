# SAT3611-Lab01
Repo for how I set up my environments for SAT3611 at Michigan Tech
# How to set up vagrant
#### by Derek Laker <dplaker@mtu.edu>

## Preamble
### What is Vagrant?
Vagrant is a tool for building and managing virtual machine environments in a single workflow. With an easy-to-use workflow and focus on automation, Vagrant lowers development environment setup time, increases production parity, and makes the "works on my machine" excuse a relic of the past.

Read more about Vagrant here:
https://www.vagrantup.com/intro/index.html

# Requirements
- vagrant
- Virtualization enabled

### Installation
Install vagrant. Depending on your operating system, this will vary.
https://www.vagrantup.com/

### Using vagrant
After installing vagrant, creating machines should be a snap. Here's a rough overview of what to do
- ```vagrant init```
- Edit the file, Vagrantfile, and change ```config.vm.box = "BOX"``` to desired box
- ```vagrant up```
- ```vagrant ssh```

### Setting up a base fedora 28 box
Assuming you already have vagrant installed. CD into the directory and run
```
vagrant init
```
Edit the Vagrant file that the previous command spawns with your favored text editor. I used vim
```
vim Vagrantfile
```
The only line we really need to worry about in that file in the following:
```
config.vm.box = "base"
```
Change this to:
```
config.vm.box = "generic/fedora28"
```
All set! Now run:
```
vagrant up
```
Vagrant will download the generic box and run it. This may take some time.

To remote into the box run:
```
vagrant ssh
```
If you need a GUI environment, go to your Virtual Manager, IE: VirtualBox/VMWare
You'll see a new vm with a name somewhat like "fed28_default_"
For VirtualBox, right click the VM and select "Show". This will show you the window just as if you were to not use vagrant in the first place.
