# Idea

"Notmuchix" aims to package any (as little as possible) manual instructions, and any (as simple and small as possible) scripts required to build (and run) a minimal (as tiny as possible, hopefully below 100MB, ideally much less) [VirtualBox](https://www.virtualbox.org/) (or similar, some VM, or something smaller if possible, but cross-platform) image containing the [notmuch email indexer](http://notmuchmail.org/), in such a way that it is possible to use it to index emails stored on host Windows OS (and ideally other OSes too).

Ideally, the OS on VirtualBox should be "declarative and immutable", thus hopefully also allowing easy upgrades, possibly thanks to use of [NixOS](http://nixos.org/) or [Guix](http://www.gnu.org/software/guix/) and/or Docker/Vagrant.

## References

- [Running the Nix package manager within a Docker Container](http://zef.me/blog/6049/nix-docker)
