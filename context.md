#### Terminology & Context

Here I'll try to unmystify Android-specific terminology and help to connect them to general Linux and computer science terminology. This should be helpful to anyone who knows about Linux or computer science, but has not begun to pull apart and understand what's in their mobile devices yet. A lot of this may be a bit excrucriating to a Linux pro, but I promise you less basic stuff is in this document if you read on. (Unless you're an mobile OS expert, in which case all of this is probably basic to you and I honestly don't know why you're reading this. Maybe you should go read something else? You'd be surprised how well-written some My Little Pony fanfiction is.)

* custom ROM
 * Just a distro (OS distribution) for a phone. The terminology was presumably invented by Android-enthusiast Windows-users who did not already have the term 'distro' in their vocabulary. I think ROM comes from Read Only Memory, which is presumably because the /system partition containing the operating system files is mounted a RO by default. There is nothing intrinsically read-only about it at the hardware level, and it can easily be rewritten if you convince the kernel to let you do so -- which is sadly becoming increasingly difficult. It is also sometimes called "custom firmware" -- although embedded systems have become so sophisticated that the distiniction between firmware and software is stupid and meaningless by now. I personally only use the term "firmware" for tiny embedded systems that have no kernel.

* Flashing
 * Just a fancy word for "writing to memory", usually to the typically read-only portions of memory that constitute the ROM or firmware or whatever.

* Bootloader (some know this, some may not...)
 * A bootloader is a piece of software responsible for loading the kernel into memory. In the case of Android, it also has lots of auxiliary functions not typically associated with a bootloader -- it can 'flash' or copy a raw image file from a traditional laptop/desktop to the phone's raw partitions. It can also do more sophisticated integrity checks, and therein lies some dangers to user freedom.

* Image (You probably know this one already, but for those who don't...)
 * A good way to understand what this is, is look at disc images files (`.iso` or `.dmg`). These are essentially bit-for-bit raw file systems containing their own directory structure and lots of files. You can think of them as similar to `.zip` files or `.tgz` files, except optimized for read performance when copied to the raw block device of a storage medium, as opposed to compression. A `.img` file is not a specific format, but rather, a file containing _some kind_ of raw filesystem image. In the case of Android, it is usually [ext4](https://en.wikipedia.org/wiki/Ext4).

* Root manager
 * A piece of software designed to manage root access on Android, asking the user if they want an app's access to be elevated. Will often have the option to store persistant access permission for specific apps.

* ADB
 * Android Debug Bridge -- basically a shitty remake of SSH that (usually) only works over USB. ADB gives you terminal access, lets you forward ports, pull and push files, and pretty much everything SSH does. It uses a public/private key system so that on a phone with debug access enabled, you can't accidentally, say, give a malicious phone charger terminal access to your phone.

* SuperSU
 * A popular closed source root manager. I recommend using LineageOS and its root manager instead.

* TWRP
 * An open source, reasonably powerful recovery distribution. Unfortunately, it has some antifeatures, such as a very misleading prompt asking you to install their shitty closed-source app.
