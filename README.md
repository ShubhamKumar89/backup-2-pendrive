# Backup to Pen Drive

To send data from your server to a pen drive using the terminal, you can follow these steps:

#### 1. Plug in your pen drive

#### 2. Identify the pen drive

Use the `lsblk` or `fdisk` command to identify your pen drive. The output will show a list of storage devices along with their mount points. Your pen drive will typically be listed as `/dev/sdb1`, `/dev/sdc1`, etc. depending on the number of storage devices connected to your server.

   ```bash
   lsblk
   ```

   or

   ```bash
   sudo fdisk -l
   ```

#### 3. Mount the pen drive

If your pen drive is not automatically mounted, you will need to manually mount it. First, create a mount point. This is a directory where your pen drive will be mounted:

   ```bash
   sudo mkdir /mnt/usb
   ```

Then, mount the pen drive to the directory you just created. Replace `/dev/sdb1` with the path that corresponds to your pen drive:

   ```bash
   sudo mount /dev/sdb1 /mnt/usb
   ```

#### 4. Transfer the data 

Now you can transfer data from your server to the pen drive. Use the `cp` command to copy files or directories. Replace `/path/to/your/data` with the path to the data you want to copy:

   ```bash
   sudo cp /path/to/your/data /mnt/usb
   ```

#### 5. Check the data

You can check if the data has been successfully copied:

```bash
ls /mnt/usb
```

#### 6. Safely remove the pen drive

Before physically removing the pen drive, it's important to unmount it safely to prevent data corruption:

   ```bash
   sudo umount /mnt/usb
   ```

Now, you can safely remove the pen drive from your server.
