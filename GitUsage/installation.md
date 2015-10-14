# How to install Git
## Section Links
* [Various Linux distro package instructions](#linux-installation-options)
* [Fedora source instructions](#fedora-source-installation)
* [Debian/Ubuntu source instructions](#debian-source-installation)
* [Debian/Ubuntu using GitHub instructions](#debian-source-install-using-github)
* [Mac Installation Options](#mac-installation-options)
* [Windows Installation Options](#windows-installation-options)

---

### Linux Installation Options
Package management installations:

    Fedora:
    $ sudo yum install Git

    Debian:
    $ sudo apt-get install git

    Gentoo:
    $ emerge --ask --verbose dev-vcs/git

    Arch Linux:
    $ pacman -S git

    openSUSE:
    $ zypper install git

    FreeBSD:
    $ cd /usr/ports/devel/git
    $ make install

    Solaris 11 Express:
    $ pkg install developer/versioning/git

    OpenBSD:
    $ pkg_add git

---

#### Compiling from source:
Compiling from source enables you to install the most recent version (binary installers tend to be behind).

**Note**: *source installations are not maintained through your package manager and will need to be manually updated and recompiled periodically*

Required Libraries: curl, zlib, openssl, expat, libiconv

##### Fedora Source Installation:
1. Install minimal dependencies
```
    $ sudo yum install curl-devel expat-devel gettext-devel openssl-devel perl-devel zlib-devel
```
2. Install additional documentation dependencies
```
$ sudo yum install asciidoc xmlto docbook2X
```
3. For Fedora/RHEL/RHEL-derivatives (due to binary name differences)
```
$ sudo ln -s /usr/bin/db2x_dockbook2texi /usr/bin/dockbook2x-texi
```
4. Next, download the latest tarball from:
    * [Kernel.org site](https://www.kernel.org/pub/software/scm/git) (has release signatures if you want to verify your download)
    * [GitHub mirror](https://github.com/git/git/releases) of the Kernel.org site (generally a little clearer regarding the latest version)
5. Compile and install
```
    $ tar -zvf git*.tar.gz
    $ cd git*
    $ make configure
    $ ./configure --prefix=/usr
    $ make all doc info
    $ sudo make install install-doc install-html install-info
```
---

##### Debian Source Installation

1. Install minimal dependencies
```
$ sudo apt-get install -y libcurl14-gnutls-dev libexpat1-dev gettext libz-dev libssl-dev
```
2. Install additional documentation dependencies
```
$ sudo yum install -y asciidoc xmlto docbook2X
```
4. Next, download the latest tarball from:
    * [Kernel.org site](https://www.kernel.org/pub/software/scm/git) (has release signatures if you want to verify your download)
    * [GitHub mirror](https://github.com/git/git/releases) of the Kernel.org site (generally a little clearer regarding the latest version)
5. Compile and install
```
    $ tar -zvf git*.tar.gz
    $ cd git*
    $ make configure
    $ ./configure --prefix=/usr
    $ make all doc info
    $ sudo make install install-doc install-html install-info
```

---

##### Debian source install using GitHub
1. Install dependencies
```
$ sudo apt-get update
$ sudo apt-get install -y build-essential libssl-dev libcurl14-gnutls-dev libexpat1-dev gettext unzip
```

3. Get Git from GitHub's [project page](https://github.com/git/git)
    1. on the right hand side of the page, right click the Download Zip button and select "Copy Link Address"
    2. In terminal type the following, using CTRL-shift-V to paste the address you copied in the previous step:
```
    $ wget https://github.com/git/git/archive/master.zip -0 git.zip
```
3. Unzip the downloaded file and move into the newly created directory
```
$ unzip git.zip
$ cd git*
```
4. Make and install the package
```
$ make prefix=/usr/local all
$ sudo make prefix=/usr/local install
```

**Note** now that git is installed, you can upgrade easily by cloning the repository as shown below, then simply follow the instructions in #4 above to make and install the package again
```
$ git clone https://github.com/git/git.git
```
---

### Mac Installation Options
1. Install the Xcode Command Line Tools
    * simply try to run *git* from the terminal. If it is  not installed, it will prompt you to install it.
2. For a more up-to-date version, use the binary installer maintained and available for download at the [Git Website](http://git-scm.com/download/mac)
3. Use the GitHub for Mac installer from the [GitHub for Mac](http://mac.github.com) website. The GitHub GUI tool has an option to install command line tools as well.

---

### Windows Installation Options
1. Use the Git for Windows project from the [Git Website](http://git-scm.com/download/win) (the download will start automatically). **Note**:This is a project called Git for Windows, which is separate from Git itself.
2. Install [GitHub for Windows](http://windows/github.com). The installer includes a command line version of Git as well as the GUI. It also works well with Powershell and sets up solid credential cashing and sane CRLF settings.
