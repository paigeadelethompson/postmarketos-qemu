# PostmarketOS for QEMU

## Usage
```
qemu-system-x86_64                                           \
-M pc                                                        \
-kernel boot/vmlinuz-edge                                    \
-initrd boot/initramfs                                       \
-append "console=ttyS0,115200n8 console=tty0 root=/dev/vda2" \
-device virtio-blk-pci,drive=system                          \
-drive if=none,id=system,file=qemu-amd64.img,id=hd0          \
-device virtio-vga-gl                                        \
-display gtk,gl=on
```
