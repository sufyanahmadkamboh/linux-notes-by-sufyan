# Partitions & Filesystems

Inspect disks

bash
Copy code
lsblk -f
sudo fdisk -l
Mount

bash
Copy code
sudo mkdir -p /mnt/data
sudo mount /dev/sdb1 /mnt/data
df -hT /mnt/data
fstab (auto-mount)

bash
Copy code
grep sdb1 /etc/fstab || echo '/dev/sdb1 /mnt/data ext4 defaults 0 2' | sudo tee -a /etc/fstab
