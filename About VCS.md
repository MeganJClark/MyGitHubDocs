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
Many people's method of local version control is to copy files into another directory.
This method is very common, but also very error prone.
* Pros
  * Very simple
* Cons
  * easy to forget which directory you're in
  * easy to write to the wrong file or copy over files
  * With the entire history of the project in one place, you risk losing everything

#### Examples
Software | Source | Software | Source
---------|--------|----------|-------
SCCS | open | RCS | open
PVCS | prop. | QVCS | prop.

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
  * If the disk holding the central database becomes corrupted, you risk losing everything
  * Tend to perform slowly when confronted with large projects

#### Examples:
Software | Source | Software | Source |
---------|--------|----------|--------|
CVS | open | Subversion | open
Vesta | open | AccuRev | prop.
Autodesk Vault | prop. | CADES | prop.
Dimensions CM | prop. | IBM RCC | prop.
IBM CMVC | prop. | IBM RTC | prop.
IC Manage | prop. | MKS Integrity | prop.
Perforce | free up to 20 users | PVCS | prop.
PVCS | prop. | Quma VCS | prop.
Razor | prop.| SourceAnywhere | prop.
StarTeam | prop. | Surround SCM | prop.
Team Foundation Server | prop. | IBM Rational Synergy | prop.
Vault | prop. | Visual SourceSafe | prop

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

#### Examples:
Software | Source | Software | Source |
---------|--------|----------|--------|
Aegis | open | ArX | open
Bazaar | open | Codeville | open
Darcs | open | DCVS | open
Fossil | open | Git | open
GNU arch | open | Mercurial | open
Monotone | open | SVK  | open
Veracity | open | BitKeeper | prop.
Code Co-op | prop. | Sun Workshop TeamWare | prop.
Plastic SCM | prop.



## Why should you care
