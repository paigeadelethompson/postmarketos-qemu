# PostmarketOS for QEMU 

## Login
User: `postmarketos`
Password: `postmarketos`

## Usage
```
qemu-system-x86_64                                              \
-nodefaults                                                     \
-nographic                                                      \
-M q35                                                          \
-m 8192M                                                        \
-smp 4                                                          \
-kernel boot/vmlinuz-edge                                       \
-initrd boot/initramfs                                          \
-append "console=ttyS0,115200n8 console=tty0 root=/dev/vda2"    \
-device virtio-blk-pci,drive=system                             \
-drive if=none,id=system,file=qemu-amd64.img,id=hd0,format=raw  \
-device virtio-gpu-gl                                           \
-display gtk,gl=on                                              \
-device usb-ehci                                                \
-device qemu-xhci                                               \
-device usb-kbd                                                 \
-device usb-mouse                                               \
-device usb-tablet                                              \
-netdev user,id=net0,net=169.254.0.0/16,dhcpstart=169.254.0.2   \
-device virtio-net-pci,netdev=net0                              \
-device ich9-intel-hda                                          \
-device hda-micro                                               \
-serial mon:stdio
```
