# CoreOS cluster via Vagrant

This repo provides a template Vagrantfile to create a CoreOS cluster using the VirtualBox software hypervisor.
After setup is complete you will have a five CoreOS virtual machines running on your local machine. Please be aware that the standard memory per instance is set to 1536 MB, and the cpu to 1.
That means by default you'll need a machine capable to free up to 5 cpus and 7680 MB memory.

## Streamlined setup

1) Install dependencies

* [VirtualBox][virtualbox] 4.3.10 or greater.
* [Vagrant][vagrant] 1.6 or greater.

2) Clone this project and get it running!

```
git clone https://github.com/mesoshq/vagrant-cluster-coreos/
cd vagrant-cluster-coreos
```

If you want to use the `cloud-config` mechanism, rename the `user-data.template` file to `user-data` and edit the file according to the [CoreOS docs](https://coreos.com/os/docs/latest/cloud-config.html).

3) Startup and SSH

The VirtualBox provider is the default Vagrant provider. Use this if you are unsure.

```
vagrant up
vagrant ssh core-01
```

**Description:**

`vagrant up` triggers Vagrant to download the latest CoreOS stable box (if necessary) and (re)launch the instances

`vagrant ssh <hostname>` connects you to the virtual machine. The hostnames are core-01 to core-05, the IPs are from 172.17.9.101 to 172.17.9.105.

4) Get started [using CoreOS][using-coreos]

[virtualbox]: https://www.virtualbox.org/
[vagrant]: https://www.vagrantup.com/downloads.html
[using-coreos]: http://coreos.com/docs/using-coreos/
