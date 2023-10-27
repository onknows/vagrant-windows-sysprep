# Vagrant Windows Sysprep Provisioner

[![Latest version released](https://img.shields.io/gem/v/vagrant-windows-sysprep.svg)](https://rubygems.org/gems/vagrant-windows-sysprep)
[![Package downloads count](https://img.shields.io/gem/dt/vagrant-windows-sysprep.svg)](https://rubygems.org/gems/vagrant-windows-sysprep)

This is a Vagrant plugin to sysprep Windows.

**NB** This was only tested with Vagrant 2.2.14 and Windows Server 2016/2019/2022 and Windows 10 1809.

# Installation

```bash
vagrant plugin install vagrant-windows-sysprep
```

# Usage

Add `config.vm.provision "windows-sysprep"` to your `Vagrantfile` to sysprep your
Windows VM during provisioning or manually run the provisioner with:

```bash
vagrant provision --provision-with windows-sysprep
```

To troubleshoot, set the `VAGRANT_LOG` environment variable to `debug`.

## Example

In this repo there's an example [Vagrantfile](Vagrantfile). Use it to launch
an example.

First install the [Base Windows 2019 Box](https://github.com/rgl/windows-vagrant).

Then launch the example:

```bash
vagrant up --provider=libvirt # or --provider=virtualbox
```

# Development

To hack on this plugin you need to install [Bundler](http://bundler.io/)
and other dependencies. On Ubuntu:

```bash
sudo apt install bundler libxml2-dev zlib1g-dev
```

Then use it to install the dependencies:

```bash
bundle
```

Build this plugin gem:

```bash
rake
```

Then install it into your local vagrant installation:

```bash
vagrant plugin install pkg/vagrant-windows-sysprep-*.gem
```

You can later run everything in one go:

```bash
rake && vagrant plugin uninstall vagrant-windows-sysprep && vagrant plugin install pkg/vagrant-windows-sysprep-*.gem
```
