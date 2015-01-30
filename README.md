# Idea

"Notmuchix" aims to package any (as little as possible) manual instructions, and any (as simple and small as possible) scripts required to build (and run) a minimal (as tiny as possible, hopefully below 100MB, ideally much less) [VirtualBox](https://www.virtualbox.org/) (or similar, some VM, or something smaller if possible, but cross-platform) image containing the [notmuch email indexer](http://notmuchmail.org/), in such a way that it is possible to use it to index emails stored on host Windows OS (and ideally other OSes too).

Ideally, the OS on VirtualBox should be "declarative and immutable", thus hopefully also allowing easy upgrades, possibly thanks to use of [NixOS](http://nixos.org/) or [Guix](http://www.gnu.org/software/guix/) and/or Docker/Vagrant.

If possible and if I find enough time; I'd really hope this'd be doable fast...

## References

- [Running the Nix package manager within a Docker Container](http://zef.me/blog/6049/nix-docker)

## Future

If I manage to pull this out, further goals would be to:

- If notmuch proves a tool fitting me enough that I use it, it'd be good if it's possible to convert it to [Go](http://golang.org) with help of the c2go hack. 
- It would be good to extend the VM with [gmvault](http://gmvault.org/), and make it work together with notmuch. That could hopefully be enough to escape gmail.
  - If not enough to escape gmail, evaluate what else is missing. Currently I suppose that'd be any or all of: spam filtering; another IMAP email client/downloader for accounts different than gmail; some tool for mail composing; some tool over notmuch for mail browsing, with attachments etc.; some tool for mail threads linking?
