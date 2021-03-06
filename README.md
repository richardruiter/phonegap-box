# phonegap-box #

A **vagrant** box provisioned with the phonegap development environment for the **android** platform. **All you have to do** is to clone the repository, fire `vagrant up` and add your android device to VirtualBox. After that you are ready to begin your phonegap project.

## Installation ##

### 1) Download and install the box ###

1. install vagrant http://docs.vagrantup.com/v2/installation/index.html
2. run `git clone git@github.com:vasconcelloslf/phonegap-box.git`
3. run `cd phonegap-box`
3. run `vagrant up`

### 2) Configure your device on the box ###

The box doesn't have an UI, so there is no emulator, you can only install on the device. In order to do so, you need to configure the VirtualBox to see your device through a USB port:

0. Plug the device
1. VirtualBox -> phonegap-box -> Settings -> Ports -> USB -> Add Filter -> (Select your android device)
2. (your device) Settings -> Developer Options -> USB Debugging (remark if it alreday marked)
3. (your device) A prompt to allow the virtual machine will appear. Click ok.
4. Plug and unplug the USB device.
5. (vagrant) run `adb devices`. You now should see your device on the list. 

In order to resolve the `?????? no permissions` problem:

* sudo -s
* adb kill-server
* adb start-server
* adb devices

### 3) Create and run your phonegap project ###

1. run `vagrant ssh`
2. run `cd /vagrant`
3. run `phonegap create folder-name -n ProjectName`
4. run `cd folder-name`
5. run `phonegap run android`

**That's it.**

## About ##

This box will install and configure the following:

* Vim
* Git
* Node.js
* Npm
* Java JRE
* Java SDK
* Android ADT
