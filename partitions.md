#### Partitions

* Recovery partition
 * Often just called a "recovery", a recovery partition is basically a mini operating system designed as a fallback for doing administrative tasks on an Android device. The built-in recovery will not offer you root access or do much of anything useful, but it will offer you the opportunity to wipe your system partition if something fucks up. That's basically all it's there for in a stock OS. In a more sophisticated setup, a recovery partition can include features like ADB shell access, touch-optimized GUI. It's usually mounted as read-only and only accessible to root users.

* System
 * This is the partition that contains your actual operating system. It's usually read-only.

* Data
 * This contains everything that isn't part of your core system. When you do a "factory reset" what you're really doing is simply wiping this partition. It's split into multiple parts -- some contain user data (e.g., `/sdcard/`is simply symlinked to `/data/media/0`

* Vendor
 * The vendor partition has some important jobs, and if you're using a custom ROM compiled against a different version, you may have to acquire a different vendor image and flash it. I learned this the hard way when I started using Nexus 5x units (which, at the time, were still getting vendor image updates).

