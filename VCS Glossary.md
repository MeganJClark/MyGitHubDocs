# VCS Glossary

**Baseline**
  An approved revision of a document or source file from which subsequent changes can be made.

**Branch**: A set of files under version control may be *branched* or *forked* at a point in time
  so that from that time forward, the copies may develop at different speeds or in different ways
  independently of each other

**Change**: (aka diff or delta) represents a specific modification to a document under version control.

**Change List**: (aka change list, change set, update, patch) identifies the set of changes made in a single commit.
This can also represent a sequential view of the source, allowing the examination of source "asof" any particular changelist.

**Checkout**: to create a local working copy from the repository. A user may specify a specific revision or obtain the latest. The term
'checkout' can be used as a noun to describe a working copy.

**Clone**: creating a repository containing the revisions from another repository. This is equivalent to *pushing* or *pulling*
into an empty repository. As a noun, two repositories can be said to be clones if they are kept syncronized and contain the same
revisions.

**Commit**: (aka check in, ci, install, submit, record) to write or merge the changes made in the working copy back into the repository. The terms *commit*
and *checkin* can also be used as nouns to describe the new revision that is created as a result of committing.

**Conflict**: occurs when different parties make changes to the same document, and the system is unable to reconcile the changes. A user must
*resolve* the conflict by combining the changes or by selecting one change in favor of the other.

**Delta Compression**: most VCS use delta compression, which retains only the differences between successive versions of files. This allows for
more efficient storage of many different versions of files.

**Dynamic Stream**: A stream in which some or all file versions are mirrors of the parent stream's versions.

**Export**: the act of obtaining the files from the repository. It is similar to *checking out* except that it creates
a clean directory tree without the version-control metadata used in a working copy. This is often used prior to publishing
the contents.

**Forward Integration**: the process of merging changes made inside the main *trunk* into a development (feature or team) branch.

**Head**:(aka tip) refers to the most recent commit, either to the trunk or to a branch. The trunk and each branch have their own head, although HEAD is sometimes
loosely used to refer to the trunk.

**Import**: the act of copying a local directory tree (that is not currently a working copy) into the repository for the first time.

**Initialize**: to create a new, empty repository.

**Interleaved deltas**: some VCS use interleaved deltas, a method that allows storage of the history of text based files in a more efficient
way than by using *Delta compression*.

**Label**: (aka tag)

**Mainline**: similar to trunk, but there can be a mainline for each branch

**Merge**: a merge or integration is an operation in which two sets of changes are applied to a file or set of files. Sample scenarios:
  * A user, working on a set of files, updates or syncs their working copy with changes made and checked into the repository by other users.
  * A user tries to check in files that have been updated by others since the files were checked out, and the VCS automatically merges the files - typically
  after prompting the user if it should proceed with the automatic merge, and some cases only doing so if the merge can be clearly and reasonably resolved
  * A branch is created, the code in the files is independently edited, and the updated branch is later incorporated into a single, unified trunk
  * A set of files is branched, a problem that existed before the branching is fixed, and the fix is then merged back into the other branch. This type of selective
  merge is sometimes known as a *cherry pick* to distinguish it from the complete merge in the previous cases.

**Promote**: The act of copying file content from a less controlled location into a more controlled location. For example, from a user's workspace into a repository or from  a steam to it's parent.

**Pull, push**: copy revisions from one repository to another. *Pull* is  initiated by the receiving repository, while *push* is initiated by the source. *Fetch* is sometimes used as a synonym for pull, or to mean a pull followed by an update.

**Repository**:(aka depot) where files' current and historical data are stored, often on a server.

**Resolve**: the act of user intervention to address a conflict between different changes to the same document.

**Reverse integration**: the process of merging different team branches into the main trunk of the CVS.

**Revision**:(aka version) any change in form.

**Share**: the act of making one file or folder available in multiple branches at the same time. When a shared file is changed in one branch, it is changed in other branches.

**Stream**: a container for branched files that has a known relationship to other such containers. Streams form a hierarchy; each stream can inherit
various properties (such as versions, namespace, workflow rules, subscribers) from it's parent stream.

**Tag**: (aka label) refers to an important snapshot in time, consistent across many files. These files at that point may be tagged with a user-friendly, 
meaningful name or  revision number.

**Trunk**: (aka Baseline, Mainline, Master) the unique line of development that is not a branch.

**Update**: (aka sync) merges changes made in the repository into the local working copy. Update is also the term used by
some CM tools (CM+, PLS, SMS) for the change package concept (*changelist*). Synonymous with *checkout* in VCS that require
each repository to have exactly one working copy (common in distributed systems).

**Working Copy**: the local copy of files from a repository, at a specific time or revision. All work done in the files in a repository is initially done
on a working copy. Conceptually it's a sandbox.
