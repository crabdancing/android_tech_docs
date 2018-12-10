# Frequently Unanswered Questions
## _It's time to give a FUQ._

#### How do you install a custom ROM?

What, like, me, _personally_, or people in general?

I'm not sure how most people do it, but I think they usually:

1. Buy phones with locked bootloaders.
 * e.g., some Samsung POS

2. Use some sort of privilege-escilation exploit to gain root access while in userspace.
 * e.g., "towelroot" or some other shady closed-source utility that might or might not be inserting malware into your kernel. No one knows.

3. Use that exploit either to write directly to a system partition to add a root manager.
 * e.g., SuperSU

4. Write to their not-currently-in-use recovery partition with a custom recovery image
 * e.g., TWRP

5. Use that custom recovery image to write to the system and boot partitions with a custom ROM.
 * Usually system and boot partitions are packaged together in a .zip as a sparse image.

#### That's a lot of steps and seems really annoying.

I agree! That's yet another reason why locked bootloaders are shit.

#### So how do I install a custom ROM with a locked bootloader?

There are many ways. Personally, in the case of Nexus devices, I unlock the bootloader with `fastboot oem unlock`. I then do `fastboot flash recovery twrp_or_whatever.img`. I can then flash the custom ROM zip file straight from TWRP's GUI, and whatever else I like.

#### I want to flash or otherwise handle a raw image file myself, but I extracted the custom ROM's zip file, and I see a lot of weird crap with extensions like `new.dat.br`! HAAALaLAP.

That's just a weirdly compressed sparse image. Basically, the core files are wrapped in like 4 different abstraction layers. It's pretty absurd. Sad to say, you'll need some special tools utilities. Get `brotli` and `sdat2img`.

Let's say you want to extract a `system.img` so it can be flashed by hand via `fastboot`:

* `brotli --decompress system.new.dat.br`
  * Creates a `system.new.dat`.
* `sdat2img system.transfer.list system.new.dat`
  * Creates a `system.img`.
  * That's all you need! You can pull apart and build a `TWRP`-style image distribution to get a set of `.img` partition files which you can then flash directly with your bootloader, if desired. Good workaround if you find your system bricked. You can also gzip these files up, push over ADB, and install manually inside TWRP, when TWRP's automated install mechanism fails. You will usually need a `boot.img` and `system.img` for any given custom ROM.
  * Oh, and you can check out the formatting by doing `file system.img` or look at filesystem structure to further identify what it is by doing `7z l system.img` or extract with `7z x system.img` or mount with... blah blah blah, I'm assuming you can work from there if you know Linux internals.
 
#### I want to manually clone to/from Android partitions, but I have like 30 partitions under `/dev/block`. What the fuck is this?

Android is aggressively modular that way. To the point of obnoxiousness. The internals are _not_ designed to be hacker friendly. But I'm sure you've realized that by now.

Here's how:

* `ls /dev/block/platform/*/by-name/ -l`
 * This gives you a list of partition names and the partition numbers they're symlinked to. You can then, for instance, `dd if=system.img of=/dev/block/mmcblk0p25`. Of course, replace image name and block device as needed.
 * Alternatively, you can simply `dd if=system.img of=/dev/block/platform/[something]/by-name/system`.

#### I have a custom repo installed but the built-in terminal is crippled. I want a native package manager! I miss the Linuxyness. This Linux is the worst Linux.

I agree. It's a very unLinuxy Linux. It's so un-Linux that it's barely Linux at all. _Totally gross._

I used to recommend chrooting to people, but Termux really is the best way to go here. By default, it is tailored to unrooted phones (irritatingly) but you can get around that with a few tweaks. For instance `pkg install root-repo` to enable root packages. (There are other packages too! See [here](https://wiki.termux.com/wiki/Package_Management) for more information). Now you can install e.g. `arp-scan` and `cryptsetup`. It's notable that there are quite a few quirks with Termux, but not nearly as many as with a chroot.
