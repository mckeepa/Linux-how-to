# Use kvm and Virt-Install in cli

Create a debian server in a virtual machine from a command line.

 - change to use local images
 - update to for linux install paramters so that no interaction is needed.

```bash
virt-install --virt-type kvm --name buster-amd64 \
--location http://deb.debian.org/debian/dists/buster/main/installer-amd64/ \
--os-variant debian10 \
--disk size=10 --memory 1000 \
--graphics none \
--console pty,target_type=serial \
--extra-args "console=ttyS0"
```

## List all Images

```bash
virsh list --all
```
## Starting Network  
```bash
# List all virtyual Networks
virsh net-list --all
```

## Starting VM 

```bash
virsh start buster-amd64  --console
```