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
