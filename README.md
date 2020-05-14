Ubuntu for Terraform and Proxmox
==================

Build a custom Ubuntu base box for Terraform+Proxmox by downloading, extracting,
tweaking, and packaging the stock Ubuntu ISO.

Based on: https://github.com/yep/vagrant-ubuntu


Build dependencies
------------------

* `curl`(1).
* `m4`(1).
* `genisoimage`(1) from the `genisoimage` package available from Debian repostiory and other package archives for Linux.
	* `mkisofs` and `xorrisofs` are alternatives that work with the same arguments as `genisoimage`.

Runtime dependencies
--------------------

The results are bootable ISO images and so should run on any `i386` or
`amd64` hardware.  They are only tested in Proxmox.

Features in the ISO
-------------------

* Configurable default user with SSH key and sudoer NOPASSWD access
* The system clock is set to UTC
* Auto partition virtual disk (/dev/vda) with LVM
* OpenSSH server is installed
* Bring up only eth1 for flexible user-net SSH port forwarding
* Includes script to auto-resize partitions to the current size of
  vitual disk /etc/auto_resize_vda.sh


Building
--------

Edit configuration in

	config.sh

Building ISO images:

	./build-iso
