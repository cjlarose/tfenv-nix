![nixos](https://socialify.git.ci/pinpox/nixos/image?description=1&descriptionEditable=My%20NixOS%20Configurations&font=Source%20Code%20Pro&forks=1&issues=1&logo=https%3A%2F%2Fpablo.tools%2Fnixoscolorful.svg&owner=1&pattern=Circuit%20Board&pulls=1&stargazers=1&theme=Light)

This repository includes all configurations for my NixOS machines. Feel free to
use parts of it as you please, but keep it mind it is intended mostly for
personal use.

# Intial Setup

The structure of this repository is meant to allow easy manual deployment.
Individual hosts are defined in `/machines/<hostname>` and will import
re-usable parts of the configuration as needed. 

**TL;DR** To use a host configuration on a fresh install, do as root:
```bash
# Add the root SSH key as deployment key to the GitHub repostory
# If root has no key yet, generate one with `ssh-keygen`
# https://github.com/pinpox/nixos/settings/keys

# Clone repository to /var/nixos-configs
git clone git@github.com:pinpox/nixos.git /var/nixos-configs

# Link desired host configuration to /etc/nixos
ln -s /var/nixos-configs/machines/kartoffel /etc/nixos
```

# Create new Machine

TODO
- Create and register keys
- Setup backup
- Setup VPN

# Hosts

| Hostname  | Location  | Configuration                     |
|-----------|-----------|-----------------------------------|
| mega      | netcup.de | [mega](./machines/mega)           |
| kfbox     | netcup.de | [kfbox](./machines/kfbox)         |
| birne     | local     | [birne](./machines/birne)         |
| porree    | netcup.de | [porree](./machines/porree)       |
| ahorn     | local     | [ahorn](./machines/ahorn)         |
| kartoffel | local     | [kartoffel](./machines/kartoffel) |

The services running on each host are documented in the host-specific
`README.md` files.

# Unmanaged Resources

The following resources are not managed or included in this repository and will
have to be put in place manually.

## Secrets in `/secrets`
```
 secrets
└──  hostname
   ├──  borg
   ├──  ssh
   │  ├──  key-backup-private
   │  ├──  key-backup-public
   │  ├──  key-root-private
   │  └──  key-root-public
   └──  wireguard
      ├──  private
      └──  public
```
