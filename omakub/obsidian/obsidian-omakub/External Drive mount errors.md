
```bash
# Finding mount label (e.g. sdb1)
lsblk
# Repairing 
sudo ntfsfix /dev/sdb1
```


**1. Check your drive's UUID:**

```bash
sudo blkid /dev/sdc1
```

**2. Clean up duplicate mounts:**

```bash
sudo umount /media/handre/MyPassport
sudo rmdir /media/handre/MyPassport
```

**3. Recreate mount point:**

```bash
sudo mkdir -p /media/handre/MyPassport
```

**4. Mount the drive:**

```bash
sudo mount -t ntfs-3g /dev/sdc1 /media/handre/MyPassport
```

**5. If step 4 works, make it permanent:**

- First check if UUID in fstab matches the one from step 1
- If different, edit fstab:

```bash
sudo nano /etc/fstab
```

- Update the UUID line to match, then test:

```bash
sudo mount -a
```

That's it! The main issue is likely mismatched UUIDs or duplicate mount points.