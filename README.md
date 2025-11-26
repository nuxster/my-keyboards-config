# Keyboard configuration with QMK firmware when using a Vial

![lotus58-0](img/lotus58-0.png)
![lotus58-1](img/lotus58-1.png)

## Current keymap
### Layer 0
![layer-0](img/layer-0.png)
### Layer 1
![layer-1](img/layer-1.png)
### Layer 2
![layer-2](img/layer-2.png)
### Layer 3
![layer-3](img/layer-3.png)

# FAQ
  - [Configure udev rule](#configure-udev-rule)
  - [First time use](https://get.vial.today/manual/first-use.html)

## Configure udev rule
```shell
apt install sudo
export USER_GID=`id -g`; sudo --preserve-env=USER_GID sh -c 'echo "KERNEL==\"hidraw*\", SUBSYSTEM==\"hidraw\", ATTRS{serial}==\"*vial:f64c2b3c*\", MODE=\"0660\", GROUP=\"$USER_GID\", TAG+=\"uaccess\", TAG+=\"udev-acl\"" > /etc/udev/rules.d/59-vial.rules && udevadm control --reload && udevadm trigger'
```
