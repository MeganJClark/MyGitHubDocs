# Version Control Systems

## What is version control
Version control systems perform the following functions:
* record changes to a file or set of files over time so you can recall specific versions later
* allows you to revert files back to a previous state
* allows you to revert the entire project to a previous state
* compare changes over time
* see who last modified something that might be causing a problem
* see who introduced an issue, and when
* easy recovery when things are broken or lost

## Types of version control
### Local version control
The simplest local version control is to simply copy the project folder and work in separate copies. It's easy, but very error prone.
* Pros
  * Very simple
* Cons
  * easy to forget which directory you're in
  * easy to write to the wrong file or copy over files
  * With the entire history of the project in one place, you risk losing everything

There were a few different LVCS created between from 1972-1991 before the CVCS models were developed.

**Local Only VCS Software**

Software|Year|Open|Software|Year|Open
---|---|---|---|---|---
SCCS|1972|yes|RCS|1982|yes
PVCS|1985|no|QVCS|1991|no

### Centralized Version Control System
Developed to enable developers to collaborate on projects. These systems have a single
server that contains all of the versioned files and a number of clients that check out the
files from that central server. For many years this has been the standard for version control.
* Pros
  * Everyone knows to a certain degree what everyone else on the project is doing
  * Administrators have fine-grained control over access
  * Far easier to administer than dealing with local databases on every client
* Cons
  * Single point of failure - if that server goes down for an hour, no one can
  work or save versioned changes to anything they're working on.
  * If the disk holding the central database becomes corrupted, and backups have failed, you risk losing everything
  * Tend to perform slowly when confronted with large projects

**Client-Server VCS Software**

Software | Year| OpenSource | Software | Year|  OpenSource |
---------|------|--------|----------|-----|---------|
CVS|1986|yes|CVSNT|1998|yes
QVCS Enterprise|1998|yes|Subversion|2000|yes
Software Change Manager|1970s|no|Panvalet|1970s|no
Endevor|1980s|no|Dimensions CM|1980s|no
DSEE|1984|no|Synergy|1990|no
ClearCase|1992|no|CMVC|1994|no
Visual SourceSafe|1994|no|Perforce|1995|no
StarTeam|1995|no|Integrity|2001|no
Surround SCM|2002|no|AccuRev SCM|2002|no
SourceAnywhere|2003|no|Vault|2003|no
Team Foundation Server|2005|no|Team Concert|2008|no

### Distributed Version Control System

* Pros
  * clients don't just check out snapshots, they fully mirror the repository (multiple backups)
  * handle several remote repositories so you can collaborate with different groups of people in
  different ways, simultaneously within the same project
  * Allows setup of several different types of workflows that aren't possible in centralized systems
  * Able to work offline (except for pushing and pulling)
  * Performing actions other than pushing and pulling is extremely fast because DVCS only needs to access the hard drive, not a remote Server
  * Committing new changesets can be done locally without anyone else seeing them. Once a group of changesets is completed, they can all be pushed at once.
  * Individuals can share changes without pushing the changes for all to see
  * Context switching using branching is simple and quick
* Cons
    * Can have so many branches for pending work that you lose track of them
    * If a project contains many large binary files that cannot be easily compressed, the space needed to store all versions can accumulate quickly
    * If a project has a very long history (50k+ changesets), downloading the entire history can take an impractical amount of time and disk space
    * Learning curve - many concepts and terms are similar to those in CVCS systems, but actual results may differ greatly from expected results

**Distributed VCS Software**

Software|Year|OpenSource|Software|Year|OpenSource|
--------|----|------|--------|----|------|
GnuArch|2001|yes|Darcs|2002|yes
DCVS|2002|yes|Arx|2003|yes
Monotone|2003|yes|SVK|2003|yes
Codeville|2005|yes|Bazaar|2005|yes
Git|2005|yes|Mercurial|2005|yes
Fossil|2007|yes|Veracity|2010|yes
TeamWare|1990s|no|Code Co-op|1997|no
BitKeeper|1998|no|Plastic SCM|2006|no
