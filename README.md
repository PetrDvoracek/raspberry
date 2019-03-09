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

clean USB's partitions
```
fdisk -l
fdisk /dev/sdX
p
d
#number (select all partitions)
```
mount device into /mnt/ and write .img file on the usb (link)[http://www.abclinuxu.cz/clanky/navody/unixove-nastroje-11-split-dd]
```
mount /dev/sdX /mnt
dd bs=4M if=<iso file> of=/dev/sdX conv=fsync
```
 - **bs** speed
 - **if** input file
 - **of** output file
 - **conv** the way of convert

### [Chroot](https://wiki.archlinux.org/index.php/Chroot)
A chroot is an operation that changes the apparent root directory for the current running process and their children. A program that is run in such a modified environment cannot access files and commands outside that environmental directory tree. This modified environment is called a chroot jail. 
```
arch-chroot /mnt
```
**could be used to set up ssh on raspberry image?**

change read-only system
```
mount -o remount, rw /
```
start ssh
```
sudo systemctl start ssh.service
```
solution of "error: Connection closed by <ip> port <port>"

```
rpi $ sudo rm /etc/ssh/ssh_host_*
rpi $ sudo dpkg-reconfigure openssh-server
```
