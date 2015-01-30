# Idea

"Notmuchix" aims to package any (as little as possible) manual instructions, and any (as simple and small as possible) scripts required to build (and run) a minimal (as tiny as possible, hopefully below 100MB, ideally much less) VirtualBox image containing the notmuch email indexer, in such a way that it is possible to use it to index emails stored on host Windows OS.

Ideally, the OS on VirtualBox should be "declarative and immutable", thus hopefully also allowing easy upgrades, possibly thanks to use of NixOS or Guix and/or Docker/Vagrant.
