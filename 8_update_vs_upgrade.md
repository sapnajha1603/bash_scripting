1. sudo apt update - Refreshing the Package List

When you run:

sudo apt update

What Happens:

    This command connects to official repositories listed in /etc/apt/sources.list.
    It downloads the latest metadata (package lists, versions, and dependencies).
    It does not install or upgrade any packages.

Example: You want to see if new updates are available for your system.

$ sudo apt update

Output Example:

Hit:1 http://archive.ubuntu.com/ubuntu focal InRelease
Get:2 http://security.ubuntu.com/ubuntu focal-security InRelease [114 kB]
Get:3 http://archive.ubuntu.com/ubuntu focal-updates InRelease [114 kB]
Fetched 228 kB in 2s (130 kB/s)
Reading package lists... Done

This output shows that the system fetched new package lists from online repositories, making your system aware of the latest versions.
2. sudo apt upgrade - Installing Available Updates

When you run:

sudo apt upgrade

What Happens:

    It checks the metadata downloaded by apt update.
    If new versions of installed packages are found, it installs those updates.
    It does not install new packages or remove old ones, only updates already installed packages.

Example: After running sudo apt update, you now want to install the available updates.

$ sudo apt upgrade

Output Example:

The following packages will be upgraded:
  openssl python3
2 upgraded, 0 newly installed, 0 to remove
Need to get 1,234 kB of archives.
Do you want to continue? [Y/n] y

Here:

    The system found updates for openssl and python3 (which are already installed).
    It downloads and installs the new versions of these packages.

Why Both Commands Are Needed:

    sudo apt update - Fetches the latest version details (just updates the list).
    sudo apt upgrade - Installs updated packages from that list.