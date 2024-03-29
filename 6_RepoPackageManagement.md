## 1. What are Software Repositories?
All the Linux distributions hosts their own software repositories. A Linux user no need to go to vendor's websites in order to download the applications unlike on Windows.

It's a centralized storage location from where the Linux systems retrieves, installs software updates and applications. These repositories contains specially compiled packages in accordance with the OS distribution and version.

## 2. What are Package Managers?

Package Manager is a tool which enables a Linux user to download, install, uninstall or upgrade software packages in an automated manner.

They play a very crucial role in Linux software management. They keep tracks of all the software's installed on you system and notify you whenever a new update or upgrade is available for an application or for the Operating system itself.

Every Linux distribution for example Ubuntu, Red Hat or Arch Linux everyone has their own Package Manager tools. We will discuss about this in coming sections.

## 3. What is a Package?

A package contain all of the necessary files, meta-data, and instructions to implement a particular functionality or software application on your system.

The place to configure software repositories on all Debian based operating systems like Ubuntu is either in /etc/apt/sources.list file or can be configured in separate files under the /etc/apt/sources.list.d/ directory. The name of the files must end with .list extension.

```
cat /ect/os-release

cd /etc/apt/

cat sources.list | more
```

- Type of Repos:

| Repository | Description |
|------------|-------------|
| Main       | Officially supported software. |
| Universe   | Community-maintained, open-source software. |
| Restricted | Supported software that may not be fully open-source. |
| Multiverse | Software that is not free, which may include proprietary and patent-encumbered software. |

- code to see:
```
> deb -> These repositories contain binaries or precompiled packages. These repositories are required for most users.
> deb-src -> These repositories contain the source code of the packages. Useful for developers.

cat sources.list | grep -v "^#" | grep -i main

cat sources.list | grep -v "^#" | grep -i universe

cat sources.list | grep -v "^#" | grep -i restricted

cat sources.list | grep -v "^#" | grep -i multiverse

```

## 4. How to add custom Repos to linux ubuntu:

- Step 1 -> Import the public key used by the package management system
- Step 2 -> Create a list file and add repository config for Jenkins
- Step 3 -> Update the repositories Run the following update command which reload the database for local package on all the repositories.

```
wget -q -O - https://pkg.jenkins.io/debian/jenkins.io.key | sudo apt-key add -
sh -c 'echo deb http://pkg.jenkins.io/debian-stable binary/ > /etc/apt/sources.list.d/jenkins.list'
apt-get update

OR

> add repo
add-apt-repository 'deb http://pkg.jenkins.io/debian-stable binary/'

> remove repo
add-apt-repository --remove 'deb http://pkg.jenkins.io/debian-stable binary/'
```



