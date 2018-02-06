# Taken from: https://wiki.centos.org/HowTos/Grub2

- The general settings can be found in `/etc/default/grub`
- List all menu entries that will be displayed on boot
    - `awk -F\' '$1=="menuentry " {print i++ " : " $2}' /etc/grub2.cfg`
    - `grep "^menuentry" /boot/grub2/grub.cfg | cut -d "'" -f2`
- The default entry is defined by the GRUB_DEFAULT line in the /etc/default/grub file.
  However, if the `GRUB_DEFAULT` line is set as saved,
  the parameter is stored in the `/boot/grub2/grubenv` file. It may be viewed by:
    - `grub2-editenv list`
- The /boot/grub2/grubenv file cannot be manually edited. Use the following command instead:
    - `grub2-set-default 2`, where `2` is the entry position
    - `grub2-editenv list`
