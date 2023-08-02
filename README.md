# GCC Cross Compiler Toolchain Build Script

This repository contains the scripts needed to compile bare metal GCC for various architectures using Linux distributions.
The GCC source is fetched from the stable branch hence, contains all the latest and stable changes.

## Before we start

**Below are the packages you'll need**

* **Ubuntu or other Debian based distros**

    To install and set GCC 10 as the default compiler, you need to:

    ```bash
    sudo add-apt-repository ppa:ubuntu-toolchain-r/test -y && sudo apt-get update
    ```

    ```bash
    sudo apt-get install flex bison ncurses-dev texinfo gcc gperf patch libtool automake g++ libncurses5-dev gawk subversion expat libexpat1-dev python-all-dev binutils-dev bc libcap-dev autoconf libgmp-dev build-essential pkg-config libmpc-dev libmpfr-dev autopoint gettext txt2man liblzma-dev libssl-dev libz-dev mercurial wget tar gcc-10 g++-10 zstd --fix-broken --fix-missing
    ```

* **Arch Linux**

    ```bash
    sudo pacman -S base-devel clang cmake git libc++ lld lldb ninja
    ```

* **Fedora**

    ```bash
    sudo dnf groupinstall "Development tools"
    sudo dnf install mpfr-devel gmp-devel libmpc-devel zlib-devel glibc-devel.i686 glibc-devel binutils-devel g++ texinfo bison flex cmake which clang ninja-build lld bzip2
    ```

## Usage

Running this script is quite simple. We start by cloning this repository:
```bash
git clone https://github.com/mvaisakh/gcc-build.git gcc-build
```
```bash
./build-gcc.sh -a <architechture>
```

LLD can be built and installed into the toolchain:

```bash
./build-lld.sh -a <architecture>
```

> As of now, I only support **arm**, **arm64** and **x86 (compiles for x86_64 only)**. This list is NOT subject to change.

> Keep in mind that this script contains just the bare minimum prerequisites.

## Credits

* [Vaisakh (original author)](https://github.com/mvaisakh/) for writing this script.
* [OSDev Wiki](https://wiki.osdev.org) for knowledge base.
* [USBHost's amazing GCC build script](https://github.com/USBhost/build-tools-gcc) for certain prerequisite dependencies.

## Contributing to this repo

You're more than welcome to improve the contents within the scripts with pull requests.
However, please contribute your changes to [Vaisakh's repository](https://github.com/mvaisakh/gcc-build) instead.

Enjoy :)
