# Git
## Who developed git
Git was developed by the Linux communtiy, and primarily by Linus Torvalds, to develop their own tool based on some of the lessons they learned while using Bitkeeper. The goals of the new system were:
* speed
* simple design
* strong support for non-linear development (thousands of parallel branches)
* able to efficiently handle large projects like the Linux kernel

## When was it developed
Git was initially developed in 2005

## Why was it developed
For most of the early lifetime of Linux kernel maintenance (1991-2002) changes to the software were passed around as patches and archived files. In 2002 the Linux kernel project began using a proprietary DVCS called BitKeeper. In 2005, the relationship between the Linux community and the commercial company broke down and the tool's free-of-charge status was revoked. This prompted the Linux community to develop their own tool.

## What makes Git different

Git is different in several respects from other VCS, including other DVCS.

### Conceptual storage
 Conceptually, most other systems store information as a list of file-based changes. They think of the information they keep as a set of files and the changes made to those files over time.

 Git thinks of data as a stream of snapshots of a miniature file system. Every time you commit, it takes a picture of what all files look like at that moment and stores a reference to that snapshot. To be efficient, if the file has not changed, Git doesn't store the file again, just a link to the identical file already has stored.

### Nearly every option is local
Most operations in Git only need local files and resources to operate. Because the entire history of the project is located on the local disk, most operations (with the exception of pushing/pulling to remote) are nearly instantaneous.

### Integrity
Everything in Git is check-summed (using a SHA-1 hash) before it is stored, then referred to by that checksum. This means it's impossible to change the contents of any file or directory without Git knowing about it. You cannot lose information or get file corruption without detection.

Nearly all actions in Git only add data to the Git database. It is difficult to get the system to do anything that is not undoable, or make it erase data in any way. As in any VCS you can lose or mess up changes you haven't commited yet, but after a change is committed, it is very difficult to lose - especially if you regularly push your database into a repository. Because of this, developers can freely experiment without the danger of severely screwing things up.
