# VCS Glossary
**Alternate Object Database**
  Via the alternates mechanism, a repository can inherit part of its object database from another object database, which is called an *alternate*

**Bare repository**
  A bare repository is normally an appropriately named directory with a .git suffix that does not have a locally checked out copy of any of the files under revision control. All of the Git administrative and control files that would normally be present in the hidden .git sub-directlry are directly present in the repository.git directory instead, and no other files are present and checked out. Usually publishers of public repositories make bare repositories available.

**Blob object**
  Untyped object, e.g. the contents of a file.

**Baseline**
  An approved revision of a document or source file from which subsequent changes can be made.

**Branch**: A set of files under version control may be *branched* or *forked* at a point in time
  so that from that time forward, the copies may develop at different speeds or in different ways
  independently of each other

**Cache** (obsolete for index)

**Chain**
  A list of objects where each object in the list contains a reference to its successor (for example, the successor of a commit could be one of its parents).

**Change**: (aka diff or delta) represents a specific modification to a document under version control.

**Change List**: (aka change list, change set, update, patch) identifies the set of changes made in a single commit.
This can also represent a sequential view of the source, allowing the examination of source "asof" any particular changelist.

**Changeset**
  Bitkeeper/cvsps speak for 'commit'. Since Git stores states rather than changes, this term is not applicable.

**Checkout**: to create a local working copy from the repository. A user may specify a specific revision or obtain the latest. The term
'checkout' can be used as a noun to describe a working copy.

**Cherry-picking**
  In SCM jargon, 'cherry pick' means to choose a subset of changes out of a series of changes (typically commits) and record them as a new series of changes on top of a different codebase. In Git, this si performed by the ```git cherry-pick``` command to extract the changes introduced by an existing commit and to record it based on the tip of the current branch as a new commit.

**Clean**
  A working tree is clean if it corresponds to the revision referenced by the current head.

**Clone**: creating a repository containing the revisions from another repository. This is equivalent to *pushing* or *pulling*
into an empty repository. As a noun, two repositories can be said to be clones if they are kept syncronized and contain the same
revisions.

**Commit**: (aka check in, ci, install, submit, record) to write or merge the changes made in the working copy back into the repository. The terms *commit*
and *checkin* can also be used as nouns to describe the new revision that is created as a result of committing.

**Commit Object**
  An object which contains information about a particular revision, such as parents, committer, author, date and the tree object which corresponds to the top directory of the stored revision.

**Commit-ish (also committish)**
  A commit object or an object that can be recursively dereferenced to a commit object. The following are all committishes: a commit object, a tag object that points to a commit object, a tag object that points to a tag object aht poitns to a commit object, etc...

**Core Git**
  Fundamental data structures and utilities of Git. Exposes only limited source code management tools.

**Conflict**: occurs when different parties make changes to the same document, and the system is unable to reconcile the changes. A user must
*resolve* the conflict by combining the changes or by selecting one change in favor of the other.

**DAG**
  Directed acyclic graph. The commit objects form a directed acyclic graph becuase they have parents (directed), and the graph of commit objects is acyclic (there is no chain which begins and ends with the same object).

**Dangling object**
  An unreachable object which is not reachable even from other unreachable objects. A dangling object has no references to it from any reference or object in the repository.

**Delta Compression**: most VCS use delta compression, which retains only the differences between successive versions of files. This allows for
more efficient storage of many different versions of files.

**Detached HEAD**
  Normally the HEAD stores the name of a branch, and commands that operate on the history HEAD represents operate on the history leading to the tip of the branch the HEAD points at. However, git also allows you to check out an arbitrary commit that isn't necessarily the tip of any particular branch. The HEAD in such a state is called *detached*.

  Note that the commands that operate on the history of the current branch (e.g. git commit to build a new history on top of it) still work while the head is detached. They update the HEAD to the point at the tip of the updated history without affecting any branch. Commands that update or inquire information about the current branch (e.g. ```git branch --set-upstream-to``` that sets what remote tracking branch the current branch integrates with) obviously do not work, as there is no (real) current branch to ask about in this state.

**Dirty**
  A working tree is said to be *dirty* if it contains modifications which have not been committed to the current branch.

**Dynamic Stream**: A stream in which some or all file versions are mirrors of the parent stream's versions.

**Export**: the act of obtaining the files from the repository. It is similar to *checking out* except that it creates
a clean directory tree without the version-control metadata used in a working copy. This is often used prior to publishing
the contents.

**Evil Merge**
  An evil merge is a merge that introduces changes that do not appear in any parent.

**Fast-forward**
  A fast-forward is a special type of merge where you have a revision and you are merging another branch's changes that happen to be a descendant of what you have. In such cases, you do not make a new mergecommit but instead just update to this revision. This will happen frequently on a remote-tracking branch of a remote repository.

**Fetch**
  Fetching a branch means to get the branch's head ref from a remote repository, to find out which objects are missing from the local object database, and to get them too. See also *git-fetch(1)*.

**Forward Integration**: the process of merging changes made inside the main *trunk* into a development (feature or team) branch.

**Git archive**
  Synonym for repository (for arch people)

**Gitfile**
  A plain file .git at the root of a working tree that points at the directory that is the real repository.

**Grafts**
  Grafts enables two otherwise different lines of development to be joined together by recording fake ancestry information for commits. This way you can make Git pretend the set of parents of a commit has is different from waht was recorded when the commit was created. Configured via the .git/info/grafts file.

**Hash**
  In the context of Git, hash is synonymous for object name.

**Head**:(aka tip, head ref) refers to the most recent commit, either to the trunk or to a branch. The trunk and each branch have their own head, although HEAD is sometimes loosely used to refer to the trunk.

**HEAD**
  The current brach. In more detail, your working tree is normally derived from the state of the tree referred to by HEAD. HEAD is a reference to one of the heads in your repository, except when using a detached HEAD, in which case it directly references an arbitrary commit.

**Hook**
  During the normal execution of several Git commands, call-outs are made to optional scripts that allow a developer to add functionality or checking. Typically, the hooks allow for a command to be pre-verified and potentially aborted, and allow for a post-notification after the operation is done. The hook scripts are found in the $GIT_DIR/hooks/ directory, and are enabled by simply removing the .sample suffix from the filename. In earlier versions of GIT you had to make them executable.

**Import**: the act of copying a local directory tree (that is not currently a working copy) into the repository for the first time.

**Index**:
  A collection of files with stat information, whose contents are stored as objects. The index is a stored version of your working tree. Truth be told, it can also contain a second, and even a third version of a working tree which are used when merging.

**Index entry**:
  The information regarding a particular file, stored in the index. An index entry can be unmerged, if a merge was started but not yet finished (i.e. if the index contains multiple versions of that file).

**Initialize**: to create a new, empty repository.

**Interleaved deltas**: some VCS use interleaved deltas, a method that allows storage of the history of text based files in a more efficient
way than by using *Delta compression*.

**Label**: (aka tag)

**Mainline**: similar to trunk, but there can be a mainline for each branch

**Master**: the default development branch. Whenever you create a Git repository, a branch named *master* is created and becomes the active branch. In most cases, this contains the local development, though that is purely by convention and not required.

**Merge**: a merge or integration is an operation in which two sets of changes are applied to a file or set of files. Sample scenarios:
  * A user, working on a set of files, updates or syncs their working copy with changes made and checked into the repository by other users.
  * A user tries to check in files that have been updated by others since the files were checked out, and the VCS automatically merges the files - typically
  after prompting the user if it should proceed with the automatic merge, and some cases only doing so if the merge can be clearly and reasonably resolved
  * A branch is created, the code in the files is independently edited, and the updated branch is later incorporated into a single, unified trunk
  * A set of files is branched, a problem that existed before the branching is fixed, and the fix is then merged back into the other branch. This type of selective merge is sometimes known as a *cherry pick* to distinguish it from the complete merge in the previous cases.
  * As a verb: To bring the contents of another branch (possibly from an external repository) into the current branch. In the case where the merged-in branch is from a different repository, this is done by first fetching the remote branch and then merging the result into the current branch. This combination of fetch and merge operations is called a *pull*. Merging is performed by an automatic process that identifies changes made since the branches diverged, and then applies all of those changes together. In cases where changes conflict, manual intervention may be required to complete the merge.
  * As a noun: unless it is a fast-forward, a successful merge results in the creation of a new commit representing the result of the merge, and having as parents the tips of the merged branches. This commit is referred to as a *merge commit* or sometimes just a *merge*

**Object**: The unit of storage in Git. It is uniquely identified by the SHA-1 of its contents. Consequently, and object cannot be changed.

**Object Database**: Stores a set of *objects* and an individual object is identified by its object name. The objects usually live in $GIT_DIR/objects/.

**Object name**:(aka object identifier) The unique identifier of an object. The object name is usually represented by a 40 character hexadecimal string. also colloquially called SHA-1.

**Object type**: One of the identifiers *commit*, *tree*, *tag*, or *blob* describing the type of an object.

**Octopus**:  To merge more than two branches.

**Origin**: the default upstream of the repository. Most projects have at least one upstream project which they track. By default *origin* is used for that purpose. New upstream updates will be fetched into remote-tracking branches named origin/name-of-upstream-branch which you can see using ```git branch -r```.

**Pack**: a set of objects which have been compressed into one file to save space or transmit efficiently.

**Pack index**: the list of identifiers and other information of the objects in a pack, to assist in efficiently accessing the contents of a pack.

**Pathspec**: pattern used to limit paths in git commands.

Pathspecs are used on the command line of "git ls-files", "git ls-tree", "git add", "git grep", "git diff", "git checkout", and many other commands to limit the scope of operations to some subset of the tree or worktree. See the documentation of each command for whether paths are relative to the current directory or top level. The pathspec syntax is as follows:
* any path matches itself
* the pathspec up to the last slash represents a directory prefix. The scope of that pathspec is limited to that subtree
* the rest of the pathspec is a pattern for the remainder of the pathname. Paths relative to the directory prefix will be matched against that pattern using fnmatch(3); in particular, * and ? can match directory separators.

For example: Documentation/*.jpg will match all .jpg files in the Documentation subtree, including Documentation/chapter_1/figure_1.jpg.

A pathspec that begins with a colon : has special meaning. In the short form, the leading colon : is followed by a zero or more *magic signature* letters (which optionally is terminated by another colon: ), and the remainder is the pattern to match against the path. The *magic signature* consists of ASCII symbols that are neither alphanumeric, glob, regex special characters, nor colon. The optional colon that terminates the *magic signature* can be omitted if the pattern begins with a character that does not belong to *magic signature* symbol set and is not a colon.

In the long form, the leading colon: is followed by a open parethesis (, a comma separated list of zero or more *magic words* and a close parenthesis ), and the remainder is the pattern to match against the path.
* top - the magic word top (magic signature: /) makes the pattern match from the root of the working tree, even when you are running the command from inside a subdirectory.

* literal - wildcards in the pattern such as * or ? are treated as literal characters.
* icase - case insensitive match
* glob - Git treats the pattern as a shell glob suitable for consumption by fnmatch(3) with the FNM_PATHNAME flag: wildcards in the pattern will not match a / in the pathname. For example, "Documentation/*.html" matches "Documentation/git.html" but not "Documentation/ppc/ppc.html" or  "tools/perf/Documentation/perf.html".

  Two consecutive asterisks (**)  in patterns matched against full pathname may have special meaning:
  * A leading ```**``` followed by a slash means match in all directories. For example,``` **/foo``` matches file or directory "foo" anywhere, the same as pattern "foo". ```**/foo/bar``` matches file or directory "bar" anywhere that is directly under directory "foo"
  * a trailing``` /**``` matches everything inside. For example,``` abc/**``` matches all files inside directory "abc" relative to the location of the .gitignore file, with infinite depth.
  * a slash followed by two consecutive asterisks then a slash matches zero or more directories. For example, ```a/**/b``` matches "a/b", "a/x/b", "a/x/y/b" and so on.
  * other consecutive asterisks are considered invalid
* exclude: after a path matches any non-exclude pathspec, it will be run through all exclude pathspec (magic signature: !). If it matches, the path is ignored.

**Parent**: a commit object contains a (possibly empty) list of the logical predecessors in the line of development. These are its parents.

**Pickaxe**: the term pickaxe refers to an option to the diffcore routines that help select changes that add or delete a given text string. Wtih the ```--pickaxe-all``` option, it can be used to view the full changeset that introduced or removed a particular line of text. See git-diff(1).

**Plumbing**: a cute name for core Git.

**Porcelain**: cute name for programs and program suites depending on core Git, presenting a high level access ot core Git. Porcelains expose more of a SCM interface than the plumbing.

**Promote**: The act of copying file content from a less controlled location into a more controlled location. For example, from a user's workspace into a repository or from  a steam to it's parent.

**Pull, push**: copy revisions from one repository to another. *Pull* is  initiated by the receiving repository, while *push* is initiated by the source. *Fetch* is sometimes used as a synonym for pull, or to mean a pull followed by an update.
 * Pulling a branch means to fetch and merge it
 * Pushing a branch means to get the branch's head ref from a remote repository, find out if it is a direct ancestor to the branch's local head ref, and in that case, putting all objects, which are reachable from the local head ref, and which are missing from the remote repository, into the remote object database, and updating the remote head ref. If the remote head is not an ancestor of the local head, the push fails.

**Reachable**: all of the ancestors of a given commit are said to be *reachable* from tht commit. More generally, one object is reachable from anotehr if we can reach the one from the other by a chain that follows tags to whatever they tag, commits to their parents or trees, and trees to the trees or blobs that they contain.

**Rebase**: to reapply a series of changes from a branch to a different base, and reset the head of that branch to the result.

**Ref**: a name that begins with refs/ (e.g refs/heads/master) that points to an object name or another ref (the latter is called a symbolic ref). For convenience, a ref can sometimes be abbreviated when used as an argument to a Git command. Refs are stored in the repository.

The ref namespace is hierarchical. Different subhierarchies are used for different purposes(e.g. the refs/heads hierarchy is used to represent local branches).

There are a few special-purpose refs that do not begin with refs/. The most notable example is HEAD.

**Reflog**: a reflog shows the local history of a ref. In other words, it can tell you what the 3rd last revision in this repository was, and what was the current state in this repository yesterday, 9:14pm.

**Refspec**: used by fetch and push to describe the mapping between the remote ref and local ref.

**Remote-tracking branch**: a ref that is used to follow changes from another repository. It typically looks like refs/remotes/foo/bar(indicating that it tracks a branch named bar in a remote named foo), and matches the right-hand-side of a configured fetch refspec. A remote tracking branch should not contain direct modifications or have local commits made to it.

**Repository**:(aka depot) where files' current and historical data are stored, often on a server.

**Resolve**: the act of user intervention to address a conflict between different changes to the same document.

**Reverse integration**: the process of merging different team branches into the main trunk of the CVS.

**Revision**:(aka version) any change in form.

**Rewind**: to throw away part of the development, i.e. assign the head to an earlier revision.

**SCM**: Source code management (tool).

**SHA-1**: "Secure Hash Algorithm 1", a cryptographic has function. In the context of Git, SHA-1 is a synonym for object name.

**Shallow repository**: A shallow repository has an incomplete history some of whose commits have parents cauterized away (in other words, Git is told to pretend that these commits do not have the parents, even though they are recorded in the commit object). This is sometimes useful when you are interested in only the recent history of a project, even though the real history recorded in the upstream is much larger. A shallow repository is created by giving the ```--depth``` option to git-clone, and its history can later be deepened with git-fetch.

**Share**: the act of making one file or folder available in multiple branches at the same time. When a shared file is changed in one branch, it is changed in other branches.

**Stream**: a container for branched files that has a known relationship to other such containers. Streams form a hierarchy; each stream can inherit
various properties (such as versions, namespace, workflow rules, subscribers) from it's parent stream.

**Symref**: "Symbolic reference". Instead of containing the SHA-1 id itself, it is of the format *ref: refs/some/thing* and when referenced, it recursively dereferences to this reference. HEAD is a prime example of a symref. Symbolic references are manipulated with the git-symbolic-ref(1) command.

**Tag**: (aka label) refers to an important snapshot in time, consistent across many files. These files at that point may be tagged with a user-friendly,
meaningful name or  revision number. In Git, a ref under refs/tags namespace that points to an object of an arbitrary type (typically a tag points to either a gag or a commit object). In contrast to a head, a tag is not updated by the commit command. A Git tag has nothing to do with a Lisp tag (which would be called an object type in Git's context). A tag is most typically used to mark a particular point in the commit ancestry chain.

**Tag object**: an object containing a ref pointing to another object, which can contain a message just like a commit object. It can also contain a (PGP) signature, in which case its called a 'signed tag object".

**Topic Branch**: a regular Git branch that is used by a developer to identify a conceptual line of development. Since branches are very easy and inexpensive, it is often desirable to have several small branches that each contain very well defined concepts or small incremental, yet related, changes.

**Tree**: either a working tree or a tree object together with the dependent blob and tree objects (i.e. a stored representation of a working tree).

**Tree object**: An object containing a list of file names and modes along with refs to the associated blob and/or tree objects. A tree is equivalent to a directory.

**Tree-ish**: (treeish) A tree object or an object that can be recursively dereferenced to a tree object. Dereferencing a commit object yields the tree object corresponding to the revision's top directory. The following are all tris-ishes: a commit-ish, a tree object, a tag object that points to a tree object, a tag object that points to a tag object that points to a tree object, etc...

**Trunk**: (aka Baseline, Mainline, Master) the unique line of development that is not a branch.

**Unmerged index**: an index which contains unmerged entries.

**Unreachable object**: an object which is not reachable from a branch, tag or any other reference.

**Update**: (aka sync) merges changes made in the repository into the local working copy. Update is also the term used by
some CM tools (CM+, PLS, SMS) for the change package concept (*changelist*). Synonymous with *checkout* in VCS that require
each repository to have exactly one working copy (common in distributed systems).

**Upstream branch**: the default branch that is merged into the branch in question (or the branch in question is rebased onto). It is configured via ```branch.<name>.remote``` and ```branch.<name>.merge```. If the upstream brach of A is origin/B sometimes we say A is tracking origin/B.

**Working Copy**: the local copy of files from a repository, at a specific time or revision. All work done in the files in a repository is initially done
on a working copy. Conceptually it's a sandbox.

**Working Tree**: the tree of actual checked out files. The working tree normally contains the contents of the HEAD commit's tree, plus any local changes that you have made but not yet committed.
