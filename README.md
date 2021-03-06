# NixOS on DigitalOcean

Copy of [https://chris-martin.org/2016/nixos-on-digitalocean](https://chris-martin.org/2016/nixos-on-digitalocean) published 5th October 2016


How to start a new NixOS droplet on Digital Ocean using nixos-infect:

* Start an Ubuntu 16.04 droplet.
* Enable ipv6.
* Add your key to ~/.ssh/authorized_keys and SSH in as root.
* Download nixos-infect:
```
wget https://raw.githubusercontent.com/mpraglowski/nixos-infect/master/nixos-infect
```
* Run nixos-infect:
```
bash nixos-infect
```
* NixOS will install (this takes a little while) and the machine will reboot.
* SSH in as root again.
* Update /etc/nixos/configuration.nix to set up things like SSH and users.
* Rebuild NixOS:
```
nixos-rebuild switch
```
* Use `passwd` to set user passwords. Remember to do this for at least one sudoer so you don't lock yourself out of the machine!
