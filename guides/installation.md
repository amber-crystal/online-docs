---
description: That feeling you get when that right tool did all the work
---

# Installation

Amber CLI offers you a set of command line tools to **create, generate, scaffold and run** your projects efficiently and fast.

## Linux

Ensure you have the necessary dependencies:

* **Git:** Use your platform-specific package manager to install `git`.
* **Crystal:** Follow the instructions to get `crystal` on this page: [Crystal Installation](https://crystal-lang.org/docs/installation/index.html)
* **NodeJS and Webpack:** `node` is an optional dependency and is used to compile JavaScript and other assets.
* **PostgreSQL:** A relational database server. Amber configures applications to use this database adapter by default, but you can switch to MySQL by passing the flag `--database mysql` when creating a new application.

Once you have these dependencies, You can build the `amber` tool from source:

### From Source

Download and install `amber`

```bash
curl -L https://github.com/amberframework/amber/archive/stable.tar.gz | tar xz
cd amber-stable/
make
sudo make install
```

If you run into an issue compiling and receive the following error: 
`Unhandled exception in spawn: fork: "Cannot allocate memory"` It may be that the system does not have enough memory resource. To resolve add a swap file:

```bash
sudo dd if=/dev/zero of=/swapfile bs=2k count=1024k
sudo mkswap /swapfile
sudo chmod 600 /swapfile
sudo swapon /swapfile
```

### For Debian & Ubuntu

* These are necessary to compile the CLI:
* `sudo apt-get install build-essential libreadline-dev libsqlite3-dev libpq-dev libmysqlclient-dev libssl-dev libyaml-dev`

> You can also install amber using [Linuxbrew](http://linuxbrew.sh/) `brew install amber`

### For RedHat & CentOS

* `sudo yum groupinstall development tools`
* `sudo yum install readline-devel sqlite-devel openssl-devel libyaml-devel gc-devel libevent-devel`

### For ArchLinux & derivates

* Install the CLI from [AUR package](https://aur.archlinux.org/packages/amber/). Dependencies are automatically installed.
* `yaourt -S amber`

You should now be able to run `amber` in the command line.

## Homebrew MacOS

```text
brew install amber
```

If you have previously installed amber with `brew`, you may need to uninstall and untap it:

```text
brew uninstall amberframework/amber/amber
brew untap amberframework/amber
```

