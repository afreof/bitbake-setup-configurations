# Yocto setups

## Get bitbake-setup

```sh
mkdir bb-setup-bbb-swupdate
cd bb-setup-bbb-swupdate
git clone https://github.com/kanavin/bitbake.git
```

## Initial configuration for bitbake-setup

Create an initial configuration for bitbake-setup:

```sh
bitbake/bin/bitbake-setup reset-settings --top-dir .
bitbake/bin/bitbake-setup change-setting --top-dir . default registry "git://git@github.com/afreof/bitbake-setup-configurations.git;protocol=ssh;branch=main;rev=main"
bitbake/bin/bitbake-setup change-setting --top-dir . default dl-dir ./.bitbake-setup-downloads
```

Alternatively just write a JSON file `bitbake-setup.conf`:

```json
[default]
registry = git://git@github.com/afreof/bitbake-setup-configurations.git;protocol=ssh;branch=main;rev=main
dl-dir = ./.bitbake-setup-downloads
```

Finally the configuration can be downloaded:

```sh
bitbake/bin/bitbake-setup init poky-bbb-fitimage --top-dir .
```

