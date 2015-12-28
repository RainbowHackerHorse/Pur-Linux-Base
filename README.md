# Pür Linux
Pür Linux is a Linux distribution consisting entirely of Upstream code. No wonky distro-specific changes, no unneeded packages in base, and best of all, no SystemD. 

Pür Linux (Pronounced Pure Linux) consists of a base system comprised of upstream pure code (GNU utils you'd expect on a Linux system, the latest vanilla Linux kernel upon packaging), and the Linux port of pkgsrc from NetBSD for ports.

Unlike other Linux distrobutions, Pür Linux uses a Base/Ports paradigm, similar to FreeBSD, wherein the base operating system is updated and maintained separately from user-installed packages. This means you can update them independantly, and package updates won't bork your OS.

Pür Linux will be distributed via Tarball in a quarterly release schedule, starting sometime in 2016.
Installation will be as simple as untarring and running setup.sh
Updating is as simple as untarring and replacing, while booted into a rescue distribution such as RIP or Finnix.

All configurations are done via plaintext files, or shell scripts.

Shells included are zsh, csh, ksh, and fish. Zsh is bash-compatible, however bash will be available via pkgsrc.

## Plans

Pür Linux will use an rc-style init system, similar to Slackware, rather than sysvinit or SystemD. We strongly encourage against infecting your system with the SystemD malware. /dev will likely be populated via eudev, Gentoo's udev fork.
While we would like to include Clang/LLVM, due to the Linux kernel being reliant on GCC-specific tweaks right now, we will be including GCC in base, with Clang available via pkgsrc. Plans will be made to transition to Clang in base as soon as is feasible.

## Installation notes
Pür Linux works great on most systems.
Please be aware of the following caveats:
As much as I'd like to include support for ZFS, the goal of Pür Linux is to be untouched from upstream.
As such, ZFS support will remain as something you can compile in yourself.
We may look at making minor changes to this policy in the future, or possibly including the support as an LKM.
If so, we will begin including the zpool and zfs management tools in Base.

As we are using pkgsrc for installed packages, Pür Linux will be placing all installed packages inside the /usr/local directory, similar to FreeBSD. /bin, /sbin, /etc, /usr/bin, and /usr/sbin will only be used for Base utilities.
As such, some scripts you download may require tweaking (We always suggest using the #!/usr/bin/env $shell shebang over hardcoded paths) to work on Pür Linux.

Pür Linux will work GREAT on Linode! Since it's just a tarball, boot into Rescue Mode and untar to the disk you created in the Linode Manager. Feel free to use the Linode kernel, rather than the kernel on disk.

## FAQ

Q: So does pkgsrc update the whole system?
A: Nope! Pür Linux breaks the traditional Linux paradigm of EVERYTHING IS A PACKAGE. I'm a FreeBSD sysadmin, and I really enjoy the separation between the Base system and 3rd party packages. While Pür Linux won't be developed in a single source tree like FreeBSD (Not much to develop folks. The goal is building and distributing Upstream code, remember?) there's still going to be separation between the Base OS (Pür Linux) and Ports (using pkgsrc)

Q: You're just trying to make Linux like $BSD
A: Yup. That's the world I come from. I started out as a Linux admin originally, but all the lack of standardization between distros made me tear my hair out. Not to mention the problems with the everything is a package way of doing things.
I like having an OS be stable and secure and regularly released, with other packages being taken care of separately.

Q: How are we sure no one tampered with anything?
A: Well, as far as the distro itself, you have to trust me. Thing is, you do that with Ubuntu/CentOS/Slackware/Gentoo already anyway. As far as releases go, each tarball will be signed, and checksummed.

Q: Can I build this from source? 
Q: Where the heck is your source code?
A: Pür Linux is built entirely from upstream! This means we won't be mirroring anything except tarballs, buildscripts, and if we absolutely have to, specific changes.
This repository will have a shellscript uploaded along with the first release, to assist you in automating the process.
As URLs change, it'll be checked for accuracy and updated with each version of Pür Linux.
This is the same shell script we use for builds.

Q: I wanna send you a message. Wat Do.
A: Email rainbow@ponix.space (This'll be changing to rainbow@hacker.horse soon enough.)
My PGP key is 0x5F94763A