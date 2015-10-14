# Git History
### Who developed git
Git was developed in 2005 by Linux Torvalds in cooperation with the Linux community.

### Why was it developed
When Linux developers lost free usage of the proprietary DVCS "BitKeeper" in 2005, they opted to develop their own tool. The goal of Git was a DVCS with the following traits:
* speed
* simple design
* strong support for non-linear development (thousands of parallel branches)
* able to efficiently handle large projects like the Linux kernel

### What makes Git different

Git is different in several respects from other VCS, including other DVCS.

1. **Git thinks about storage differently** Instead of keeping a set of files and records of the changes to those files over time, Git keeps snapshots of the entire file system at a given moment. To increase efficiency, git does not store duplicates, bit instead stores a link to the identical file already in storage.

2. **No network connection needed** *(for most things)*. Other than pushing to and pulling from remote repositories, all Git commands are usable locally without a connection. This enables developers to work where they are, regardless of connection, make commits, view histories, and only push/pull when a connection is available. Additionally, because the entire history of the project is on the local disc, most operations are nearly instantaneous.

3. **Integrity is key** Git uses SHA-1 hash to checksum all files before they are stored, then each file is referenced by that checksum. Because of this, it is impossible for the contents of any file or directory to change or be corrupted without detection.

    Almost all commands add data to the Git database; as a result it is very difficult to do anything irreversible or to erase data. You can, of course, lose changes that are uncommitted, but if you regularly push to your repository it is very difficult to lose tracked data. This means you can freely branch, experiment and play without the risk of breaking important things.
