# VMWare Workstation 16.4 Pro Installation on Fedora 36

## Pre-Reqs
```
# Check if Secure Boot is enabled
dmesg | grep -i secure
#[    0.000000] secureboot: Secure boot disabled
#[    0.020452] secureboot: Secure boot disabled

# If Secure Boot is enable, google for signing kernel modules...

# If you are on a fresh Fedora 36 Install
mkdir -p /etc/init.d

# Bare minimum deps
sudo dnf install -y kernel-devel-$(uname -r) kernel-headers gcc gcc-c++ make git
```

## Install
```sh
sudo bash ./VMware-Workstation-Full-16.2.3-19376536.x86_64.bundle --eulas-agreed --required 
```

## Install Kernel Modules
```sh
sudo CPATH=/usr/src/kernels/$(uname -r)/include/linux vmware-modconfig --console --install-all
```

### Helpful  Links
[Fedora Quick-Docs](https://docs.fedoraproject.org/en-US/quick-docs/how-to-use-vmware/)  
[VMWare Communities](https://communities.vmware.com/t5/VMware-Workstation-Pro/Compiling-vmmon-module-fails-on-linux-kernel-5-16-0-arch1-1/td-p/2887820)