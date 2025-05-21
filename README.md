# Create and Run a Virtual Vachine with QEMU

### Create hard disk image.
```cosole
qemu-img create -f qcow2 ubuntu-vm.qcow2 20G
```
### How to install a Ubuntu using QEMU.
```console
qemu-system-x86_64 \
                    -m 4G \
                    -cpu host \
                    -enable-kvm \
                    -drive file=ubuntu-vm.qcow2,format=qcow2 \
                    -cdrom /home/<my home>/Downloads/ubuntu-24.04-live-server-amd64.iso \
                    -boot d \
                    -vga virtio \
                    -display vnc=:1
```

#### Start the VM with default ethernet
```console
qemu-system-x86_64 \
                -m 4G \
                -cpu host \
                -enable-kvm \
                -drive file=ubuntu-vm.qcow2,format=qcow2 \
                -boot d \
                -vga virtio \
                -display vnc=:1
```

### Connect to the virtual machine using VNC.