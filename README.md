# esxi-lift
Ability to launch different VMware ESXi hosts for testing etc.

### Requirements

* Vagrant - 2.0+ - The Vmware_Desktop plugin installed with a valid license
  * https://www.vagrantup.com/vmware/index.html
* Ansible - 2.5+
* Virtualization enabled in BIOS

See [Installing Vagrant](docs/vagrant.md) for installation instructions.

### Quickstart

This will walk through the simplest path of spinning up a production test environment of a bleeding edge nightly installation assuming Vagrant and Libvirt are installed and configured.

```
git clone https://github.com/theforeman/forklift.git
cd forklift
vagrant up centos7-foreman-nightly
```

The same can be quickly done for a development environment where GITHUB_NICK is your GitHub username:

```
git clone https://github.com/theforeman/forklift.git
cd forklift
cp vagrant/boxes.d/99-local.yaml.example vagrant/boxes.d/99-local.yaml
sed -i "s/<REPLACE ME>/GITHUB_NICK/g" vagrant/boxes.d/99-local.yaml
vagrant up centos7-devel
```
