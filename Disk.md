# Disk Management 

- [ ] How to check the disk ?
```sh
lsblk
```
- [ ] Check all directory attched as well
```sh
df -h
```
- [ ] How to use a newly added disk ?
- [ ] Format the disk
```sh
mkfs.ext4  <diskname>

mkfs.xfs <diskname>
```
- [ ] Create a directory
```sh
mkdir <directory name>
```
- [ ] Mount the disk to directory
```sh
mount <disk>  <directory>

```

- [ ] Now check
```sh
df -h
```
- [ ]  Now mount permananently
```sh
vi /etc/fstab
<diskname>    <directoryname>   filesystem    defaults   0   0
```
<img width="951" height="154" alt="image" src="https://github.com/user-attachments/assets/5fb3e520-788c-4381-be31-4798ec380627" />
