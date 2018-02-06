Taken from:
- https://www.ostechnix.com/install-linux-kernel-4-14-lts-rpm-deb-based-systems/
- https://www.tecmint.com/install-upgrade-kernel-version-in-centos-7/

The latest Kernel is not available in the official repositories. So, we need to add ELRepo repository to install this latest Kernel.

1. `rpm --import https://www.elrepo.org/RPM-GPG-KEY-elrepo.org`
2. `rpm -Uvh http://www.elrepo.org/elrepo-release-7.0-3.el7.elrepo.noarch.rpm`

List all availiable kernels:
- `yum --disablerepo="*" --enablerepo="elrepo-kernel" list available`

`ml` stands for 'mainline stable'

- `yum install yum-plugin-fastestmirror`
- `yum --enablerepo=elrepo-kernel install kernel-ml`
