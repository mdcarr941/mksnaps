## INSTALLATION
0) If using btrfs, edit your fstab to mount the btrfs partition you want to backup.
1) Build and install the package.
2) Edit /etc/mksnaps.conf appropriately for your setup.
3) Enable the appropriate service (but not both):
  systemctl enable mksnaps-btrfs
  systemctl enable mksnaps-lvm
4) If you're booting with grub, then set the variables at the top of /boot/grub/mksnaps.cfg
and edit /boot/grub/custom.cfg to source /boot/grub/mksnaps.cfg.

## USAGE
Boot from an entry defined in mksnaps to take snapshots of configured volumes.
