## Install Linux on usb form Windows

clean USB
```
diskpart
select disk #
clean
```
create partition
```
CREATE PARTITION PRIMARY
SELECT PARTITION 1
ACTIVE
FORMAT FS=FAT32 QUICK
```
## Install Linux on usb from Linux

### [Chroot](https://wiki.archlinux.org/index.php/Chroot)
A chroot is an operation that changes the apparent root directory for the current running process and their children. A program that is run in such a modified environment cannot access files and commands outside that environmental directory tree. This modified environment is called a chroot jail. 
```
arch-chroot /mnt
```
**could be used to set up ssh on raspberry image?**
