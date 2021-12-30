---
toc: true
layout: post
categories: [ubuntu]
title: Full encrypted hard drive with Ubuntu 12.04
---

Last week we got new notebooks at work. With being more mobile, there is also the risk that your precious data will be stolen with your notebook. So there is definitely the need for a encrypted hard drive!

When you are installing Ubuntu, you have the possibility to encrypt (only) your home directory. If you do not bother having the rest of your system not encrypted, you can stop here.

For a full encrypted system you will need to get the [alternate installer](http://releases.ubuntu.com/12.04/). This isn't as shiny as the "normal" installer (on which Canonical and the community did a great job), but I've the feeling that the alternate installer is much faster. But more important, this is needed to configure your partitions to be encrypted.

Short summary of the steps you will need to do:

1.  Boot into the alternate installer
2.  Get through the process until you get to the point where you have to choose how you want to partition your drives
3.  Choose manual partitioning
4.  Create a boot partition (doesn't need to be bigger than 256MB - mount on /boot)
5.  Create a physical volume for encryption (its like creating a partition).
6.  Configure the encrypted device you just created. This includes choosing a pass phrase which you will need to enter everytime you start your system. Don't spare at length or complexity of your password!
7.  Now you will need to configure the encrypted volume to be used as "physical volume for LVM" (Logical Volume Manager)
8.  Create a volume group within the LVM
9.  Now you can easily create partitions for root, home and (if you need to) swap
10. Continue with installation :)

This [video](http://www.youtube.com/watch?v=k5pjKoy0df4&feature=related) helped me a lot understanding the different steps.

The only thing that bothers me is a little bug: The prompt for inputing the pass phrase does not show up when using the quiet splash. But it is there - so you can still type in your pass phrase. You can also choose to deactivate the quiet splash :)
