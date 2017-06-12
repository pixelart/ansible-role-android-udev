# Ansible Role: platform.sh CLI

[![Build Status](https://travis-ci.org/pixelart/ansible-role-android-udev.svg?branch=master)](https://travis-ci.org/pixelart/ansible-role-android-udev)

Configures udev rules to connect Android devices, whether you use the Android Studio/SDK or not. See https://developer.android.com/studio/run/device.html#setting-up

## Role Variables

Available variables are listed below, along with default values (see `defaults/main.yml`):

    android_udev_vendor_ids:
      - name: HTC
        id: '0bb4'

A hash map of vendor name and the `ATTR{idVendor}` attribute value. Make sure the id is quoted as string, so the YAML parser will not interpret it as an octal or whatever number. This is already configured with the complete list from https://developer.android.com/studio/run/device.html#VendorIds

## Dependencies

None.

## Example Playbook

    - hosts: devs
      roles:
        - pixelart.android-udev

After the playbook runs, the udev rules are placed into `/etc/udev/rules.d/51-android.rules` and connected Android devices should be accessible by the user.

## Code of Conduct

Please note that this project is released with a [Contributor Code of Conduct](CODE_OF_CONDUCT.md). By participating in this project you agree to abide by its terms.

## License

MIT, see the [LICENSE](LICENSE) file.

## Author Information

This role was created in 2017 by [pixelart GmbH](https://www.pixelart.at/) and inspired by the roles of [Jeff Geerling](https://www.jeffgeerling.com/), author of [Ansible for DevOps](https://www.ansiblefordevops.com/).
