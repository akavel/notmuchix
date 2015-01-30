# Idea

"Notmuchix" aims to package any (as little as possible) manual instructions, and any (as simple and small as possible) scripts required to build (and run) a minimal (as tiny as possible, hopefully below 100MB, ideally much less) [VirtualBox](https://www.virtualbox.org/) (or similar, some VM, or something smaller if possible, but cross-platform) image containing the [notmuch email indexer](http://notmuchmail.org/), in such a way that it is possible to use it to index emails stored on host Windows OS (and ideally other OSes too).

Ideally, the OS on VirtualBox should be "declarative and immutable", thus hopefully also allowing easy upgrades, possibly thanks to use of [NixOS](http://nixos.org/) or [Guix](http://www.gnu.org/software/guix/) and/or Docker/Vagrant.

Or not.

## TinyCoreLinux on Vagrant/VirtualBox?

### Initial manual attempts

Download http://www.tinycorelinux.net/6.x/x86/release/Core-current.iso. (version 6.x, x86; "micro core", i.e. no X Windows).

# BOO, FAIL: don't know how to install VirtualBox Guest Additions on TinyCoreLinux, and those are required in order to enable shared folders :(

Goal idea:

- boot VirtualBox from the TCL .iso
- make VirtualBox mount a shared directory from Windows, where .tcz files will be stored (should get mounted as /tce; see `tce=...` boot code of TCL)
- use `restore=...` boot code of TCL to store the dump of local disk on Windows shared folder? or `home=...` boot code?
- https://firewallengineer.wordpress.com/2013/08/18/how-to-install-virtualbox-guest-additions-in-tiny-core-linux/ and use option `--nox11` when installing the .run file


### See also...

- https://packer.io/docs/builders/virtualbox-iso.html - for building a VirtualBox (or Vagrant/Docker) image from an .iso in an automated way. Packer.io is written in Go, so should be cross-platform (seems to have an official Windows build). Still, seems it needs an external VirtualBox instance to build on.
- http://www.tinycorelinux.net/ports.html - info about 64-bit builds of Tiny Core Linux
- [Install TinyCoreLinux on VirtualBox - Step by Step](https://machinelearning1.wordpress.com/2012/12/14/install-tinycore-linux-on-virtualbox-step-by-step/)
- [The TinyCoreLinux Book](http://www.tinycorelinux.net/book.html)

## References

- **[Declaratively Provision Docker Images Using Nix](http://zef.me/blog/6049/nix-docker)**
  - Example use: [Deploying Wordpress Using nix-docker](http://zef.me/6079/deploying-wordpress-using-nix-docker)
- [Purely Functional Configuration Management with Nix and NixOS](http://www.infoq.com/articles/configuration-management-with-nix)
- *["NixOS Vagrant Plugin"](https://github.com/zimbatm/nixbox)* ?
- *["NixOS boxes for Vagrant"](https://github.com/zimbatm/nixbox)* ?
- *["Installing NixOS in a VirtualBox guest"](https://nixos.org/wiki/Installing_NixOS_in_a_VirtualBox_guest)* ? According to this wiki, NixOS in VirtualBox requires *"New Hard Disk of 8 GB or higher."*!!! Much too much...
- *["Quickstart instructions for provisioning NixOS using virtualbox + vagrant"](https://gitlab.com/theerasmas/nixos-vagrant-quickstart/tree/master)* ?
- *["Running the Nix package manager within a Docker Container"](http://aaronlevin.ca/post/100703631408/running-the-nix-package-manager-within-a-docker)* ? This is based on a Debian Docker image unfortunately, so most probably too big.
- *["Boot2Docker"](https://github.com/boot2docker/boot2docker)* ? "Boot2Docker is a lightweight Linux distribution made specifically to run Docker containers. It runs completely from RAM, is a small ~24MB download and boots in ~5s (YMMV)."
- Some random [Nixos configuration.nix files](https://lastlog.de/wiki/index.php/Nixos_configuration.nix)
- ([NixOS and Stateless Deployment ](http://gfxmonk.net/2015/01/03/nixos-and-stateless-deployment.html) - a NixOS introductory article.)

- **[Tiny Core Linux](http://www.tinycorelinux.net/)**
- [Vagrantfile for Tiny Core Linux](https://github.com/hyamamoto/virtual-core/blob/master/vagrantfiles/Vagrantfile-tinycore)

- Headless VirtualBox: [Running VirtualBox Guest VMs In Headless Mode](https://nfolamp.wordpress.com/2010/06/10/running-virtualbox-guest-vms-in-headless-mode/)
- [Headless Debian VirtualBox Setup](http://hempeldesigngroup.com/embedded/stories/headless-debian-virtualbox-setup/) ?

## Future

If I manage to pull this out, further goals would be to:

- If notmuch proves a tool fitting me enough that I use it, it'd be good if it's possible to convert it to [Go](http://golang.org) with help of the c2go hack. 
- It would be good to extend the VM with [gmvault](http://gmvault.org/), and make it work together with notmuch. That could hopefully be enough to escape gmail.
  - If not enough to escape gmail, evaluate what else is missing. Currently I suppose that'd be any or all of: spam filtering; another IMAP email client/downloader for accounts different than gmail; some tool for mail composing; some tool over notmuch for mail browsing, with attachments etc.; some tool for mail threads linking?

