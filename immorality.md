#### What the fuck is up with this goddamn stupid market?

No one understands how computers work. They're magic boxes that let you do work for awhile, and then they mysteriously slow down and stop working and then you have to buy a new one. That's how the mobile market wants you to see computers, and it's especially how Apple wants you to see them.

But that's total garbage. Computers are _general purpose machines_ that can be configured to have absolutely _any behavior_ as long as they have the right system resources.

For instance. In theory, want a computer to forward packets to another? Sure thing! Want it to move those packets over USB, bluetooth, wifi? You got it! 

In practice? You might find that your smartphone will refuse to let you tether unless your data provider gives you permission. People don't understand information theory, so they don't realize that this is in fact complete nonsense. There isn't some sort of Magical Packet that has to be shaped right for a laptop to be able to recieve it. The phone's software is simply programmed to _refuse_ to route the packets unless the data provider tells it "psst, they forked over the money. You can forward the packets now."

In other words, the phone isn't working for you. _It's working for them._

And it goes further. Your device can be configured to show you ads even if you don't want them. Sure, it makes money for developers -- which is great -- but it "makes money" by hijacking hardware that you paid for, to relay messages from ad networks from company divisions that try to track and manipulate potential customers to maximize their profit margins. I don't know about you, but that doesn't seem like a good deal to me. I'd rather pay money for tools that I control rather than get free tools that "charge me" with antifeatures.

And thus, the locked bootloader was born. The program that's responsable for booting your phone's operating system into memory, and all outside communication with other devices, often has a built-in public key from the OEM, which it uses to check each partition image it's handed before flashing it. Because of this, for major Android device manufacturers, you are prevented from putting any operating system on the machine that they don't give you permission to use Why? Because if you were able to root, you would be able to tell the device to route packets _where you want them to go_ -- instead of where the data provider wants them to go. So the data providers used their influence to make damn sure that consumers did not have control over their devices.

It goes even further in the case of IOS devices, which are designed to require a cryptographic handshake with Apple's servers before upgrading/downgrading IOS versions. This means you literally cannot downgrade to an old "legitimate" version of IOS. Why? I'm not sure, but I suspect it has something to do with the fact that old versions of IOS have known exploits that might allow someone to get root access to their own device... which Apple considers bad because... what? Whatever the reason is, it's not in _your_ interest, is it?

Even though there are independent dev teams willing to maintain devices after the OEM has stopped supporting them, they often struggle to do so because the software on these devices cannot be changed. This means they are sitting ducks for any exploit that is discovered after support is dropped. Their security will keep continually dropping indefinitely.

It's also not unheard of for OEMs to deliberately release software updates that _reduce phone performance_ or otherwise interfere with its functionality, which they of course do right before device support is dropped -- thus of course encouraging people to buy the "upgraded" device. This creates lots of waste, costs people lots of money, and helps no one but the OEM. Planned obselecense, yo.

Fun fact: these people have also been lobbying to make rooting devices _illegal_. It's all about the company retaining control of the device _after you bought it_ so they can maximize profits in as many ways as possible.

This is why which phone you buy is so important. So, I recommend an old Nexus or similar -- do research of course, and make sure you can return it if the bootloader is locked. It's a violation of your rights and I advise everyone to refuse such things. Even if you don't need root access, the bootloader being locked means you can't do anything to upgrade the software without permission of the OEM. It hurts everyone and helps no one except the OEMs and cellular networks -- who are _pure fucking evil_.

As of this writing, a new phone called the Librem 5 is coming out that is designed to respect user rights -- it is entirely open-source and is probably one of the most secure and trustworthy mobile devices available, from a government-backdoor standard. It's a whopping 600 USD to preorder (not a great option for someone as food-insecure as me), but I'm honestly tempted to buy it anyway. You can find it [here](https://puri.sm/products/librem-5/).

But barring that, use a Nexus device or similar. The first question you should be asking when you buy it is, "does it have a locked bootloader?"
