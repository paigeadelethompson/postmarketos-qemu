# PostmarketOS for QEMU 

## Login
User: `postmarketos`
Password: `postmarketos`

## Usage
```
qemu-system-x86_64                                              \
-M pc                                                           \
-m 2g                                                           \
-smp 4                                                          \
-kernel boot/vmlinuz-edge                                       \
-initrd boot/initramfs                                          \
-append "console=ttyS0,115200n8 console=tty0 root=/dev/vda2"    \
-device virtio-blk-pci,drive=system                             \
-drive if=none,id=system,file=qemu-amd64.img,id=hd0,format=raw  \
-device virtio-vga-gl                                           \
-display gtk,gl=on                                              \
-device qemu-xhci                                               \
-device usb-kbd                                                 \
-device usb-mouse                                               \
-device usb-tablet                                              \
-netdev user,id=net0,net=192.168.76.0/24,dhcpstart=192.168.76.9 \
-device virtio-net-pci,netdev=net0                              \
-device ich9-intel-hda                                          \
-device hda-micro                                               \
-serial mon:stdio
```
