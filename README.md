# ghtr-accessibility-vagrant-base

This repo provides a configured vagrant vm that comes configured with accessibility testing tools for Windows.  The image is based on the official Microsoft provided Windows 10 vagrant image.

This vagrant machine is for local laptop usage only.  All of the details below cover how to build a base image for publishing.

## Pre-requesits:

- Vagrant
- VirtualBox
- Microsoft Remote Desktop client (v10+) (or other appropriate RDP client)

## Installing pre-requesits (macOS):

`brew cask install vagrant`

`brew install virtualbox`

## Credentials:

Credentials for the VM are configured to use the environment variable `$VAGRANT_PASS`.  This should be set before the script is ran, and have no restrictions or validation rules.  On macOS this can be with the following line a terminal window:

`VAGRANT_PASS=Passw0rd!`

And checked:

`echo $VAGRANT_PASS`

## Running the VM:

`vagrant up`

`vagrant rdp`

Note: macOS seems to need to run `vagrant rdp` twice to get the Microsoft client to connect.

## Publishing

To build, first you need to figure out the name of the image in virtualbox, to do this run:

`vboxmanage list vms`

To package:

`vagrant package --base NAME_FROM_VBOXMANAGE --output win10_accessibility_base.box`

This can now be published on VagrantCloud.

## Using the published VM:

https://app.vagrantup.com/stevewalton/boxes/win10-accessibility
