# CoreOS cluster via Vagrant

This repo provides a template Vagrantfile to create a CoreOS cluster using the VirtualBox software hypervisor.
After setup is complete you will have a three CoreOS latest stable virtual machines running on your local machine. Please be aware that the standard memory per instance is set to 3072 MB, and the number of cpus to 2. That means by default you'll need a machine capable to free up to 6 cpu cores and 9216 MB memory.

## Streamlined setup

### Install dependencies

* [VirtualBox][virtualbox] 4.3.10 or greater.
* [Vagrant][vagrant] 1.6 or greater.

### Clone this project and get it running!

```
git clone https://github.com/mesoshq/vagrant-cluster-coreos/
cd vagrant-cluster-coreos
```

If you want to use the `cloud-config` mechanism, rename the `user-data.template` file to `user-data` and edit the file according to the [CoreOS docs](https://coreos.com/os/docs/latest/cloud-config.html).

### Startup and SSH

The VirtualBox provider is the default Vagrant provider. Use this if you are unsure.

```
vagrant up
vagrant ssh core-01
```

#### Description

`vagrant up` triggers Vagrant to download the latest CoreOS stable box (if necessary) and (re)launch the instances

`vagrant ssh <hostname>` connects you to the virtual machine. The hostnames are core-01 to core-03, the IPs are from 172.17.9.101 to 172.17.9.103.

#### mesosctl

You can use the provided `mesosctl.yml` file to load the cluster configuration like this:

    mesosctl $ config load /path/to/mesosctl.yml

[virtualbox]: https://www.virtualbox.org/
[vagrant]: https://www.vagrantup.com/downloads.html
