Toolbox2docker
==================================

[![docker toolbox logo](https://cloud.githubusercontent.com/assets/251292/9585188/2f31d668-4fca-11e5-86c9-826d18cf45fd.png)](https://www.docker.com/toolbox)


This is a fork of Docker Toolbox (https://github.com/docker/toolbox)

See [Ceasing Support and Development of Docker Toolbox #898](https://github.com/docker/toolbox/issues/898)

Why a fork? I still find it useful.

NOTE: docker-machine will pull by default the obsoleted boot2docker project ISO.

To get around this issue you will need to use the docker-machine option to point
the URL to the boot2docker.iso file that ships with this toolbox2docker distribution
and manually create a virtual machine.

	docker-machine create -d ${VIRTUAL_DRIVER} ${VIRTUAL_MEMORY} \
	--${VIRTUAL_DRIVER}-boot2docker-url "file://some/path/to/file" \
	${VIRTUAL_CPU_COUNT} ${VIRTUAL_SWITCH} ${VM_MACHINE_NAME}

	--${VIRTUAL_DRIVER}-boot2docker-url "file://path/to/boot2docker.iso"
	
	where ${VIRTUAL_driver} is the driver for the Virtual machine software you are using
		virtualbox
		vmware
		vmwarefusion
		hyperv

This will also give your VM the XFS filesystem instead of EXT4 as it will be
created with the correct ISO.

The location of the boot2docker ISO on a default install:

	macOS: /usr/local/share/boot2docker/boot2docker.iso
	windows: /c/Program Files/toolbox2docker/boot2docker.iso

XXX TODO: fix documentation


The Toolbox2docker installs everything you need to get started with
Docker on Mac OS X and Windows. It includes the Docker client, Compose,
Machine, Kitematic, and VirtualBox.

## Installation and documentation

Documentation for Mac [is available here](https://docs.docker.com/toolbox/toolbox_install_mac/).

Documentation for Windows [is available here](https://docs.docker.com/toolbox/toolbox_install_windows/). 

*Note:* Some Windows and Mac computers may not have VT-X enabled by default. It is required for VirtualBox. To check if VT-X is enabled on Windows follow this guide [here](http://amiduos.com/support/knowledge-base/article/how-can-i-get-to-know-my-processor-supports-virtualization-technology). To enable VT-X on Windows, please see the guide [here](http://www.howtogeek.com/213795/how-to-enable-intel-vt-x-in-your-computers-bios-or-uefi-firmware). To enable VT-X on Intel-based Macs, refer to this Apple guide [here](https://support.apple.com/en-us/HT203296).
Also note that if the Virtual Machine was created before enabling VT-X it can be necessary to remove and reinstall the VM for Docker Toolbox to work.

Toolbox is currently unavailable for Linux; To get started with Docker on Linux, please follow the Linux [Getting Started Guide](https://docs.docker.com/linux/started/).

## Building Toolbox2docker

Toolbox2docker installers are built using Docker, so you'll need a Docker host set up. For example, using [Docker Machine](https://github.com/docker/machine):

```
$ docker-machine create -d virtualbox toolbox
$ eval "$(docker-machine env toolbox)"
```

Then, to build Toolbox2docker for both platforms:

```
make
```

Build for a specific platform:

```
make osx
```

or

```
make windows
```

The resulting installers will be in the `dist` directory.

## Frequently Asked Questions

**Do I have to install VirtualBox?**

No, you can deselect VirtualBox during installation. It is bundled in case you want to have a working environment for free.
