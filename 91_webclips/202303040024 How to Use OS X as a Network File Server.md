---
created: 2023-03-04T00:24
author: human
---

#_GTD_0_inbox

Created on: [[20230304]]
Who's involved: 
About what: 

My note: 

Author: Tom Nelson
Source: 
https://www.lifewire.com/using-os-x-as-file-server-for-network-2260170
Retrieved 

> File servers come in many forms, from dedicated computer systems like Apple’s Xserve to NAS (Network Attached Storage) hard-drive-based systems.

# How to Use OS X as a Network File Server
File servers come in many forms, from dedicated computer systems like Apple’s Xserve to cheap NAS (Network Attached Storage) hard-drive-based systems. But while buying a preconfigured solution is an option, it’s not always the best solution.

One easy solutions is to concert an old Mac into a file server. This allows you to back up files, share printer access, replace a network router, and share attached peripherals, among other tasks. If you would like to have a file server on your network, so you can share files, music, videos, and other data with other local devices, you can follow this step-by-step guide to repurpose an older Mac.

## Using macOS as a File Server: What You Need

-   **macOS**: Most [versions of macOS or OS X](https://www.lifewire.com/what-is-macos-4691239) already incorporate the software necessary for file sharing. This will make installing and configuring the server as easy as setting up a desktop Mac.
-   **An Older Mac**: The Mac should be able to run OS X 10.5 (Leopard) or later and support additional hard drives. They can either be external hard drives connected via Thunderbolt or USB, or internal hard drives for desktop Macs.
-   **A Large Hard Drive**: The size and number of drives depend on your needs, but it's a good idea not to scrimp. You can find 1 TB drives for well under $100, and you’ll fill them up faster than you think.

## Using macOS As a File Server: Selecting the Mac to Use

For most people, this decision is determined by whatever Mac hardware they have on hand. Luckily, a file server doesn’t need a great deal of processing power in order to perform effectively. That being said, there are a few hardware specs that would help our file server perform at its best.

-   **Network Speed**: Your file server should be one of the faster nodes on your network. This will ensure that it can respond to requests from multiple Macs on the network in a timely fashion. A network adapter that supports Fast Ethernet (100 Mbps) should be the minimum. If your network supports Gigibit Ethernet, then any Mac with built-in Gigibit Ethernet would be a great choice
-   **Memory**: Memory is not an important factor for a file server. Just make sure you have enough RAM to run macOS without bogging down. One GB of RAM would be the minimum; 2 GB should be more than sufficient for a simple file server.

Desktops make better servers but a laptop will also work. The only real problem with using a laptop is that its drive and internal data buses are not designed for speed. You can get around some of these issues by using one or more external hard drives connected via Thunderbolt or USB

## Using macOS as a File Server: Hard Drives to Use With Your Server

Choosing a hard drive ay be as simple as working with whatever you have installed in the Mac. You can also add one or more internal or external drives. If you’re going to buy additional hard drives, look for ones rated for continuous (24/7) use. These drives are sometimes referred to as ‘enterprise’ or ‘server’ class drives. Standard desktop hard drives will work as well, but their expected lifetime will be reduced since they are being used in continuous duty, which they were not designed for.

 Wikimedia Commons

-   **Internal Hard Drives**: If you’re going to be using a desktop Mac, you have some options for the hard drive, including speed, connection type, and size. You will also have a choice to make regarding hard drive cost. Later Mac desktops use hard drives with SATA connections. Earlier Macs used PATA-based hard drives. If you plan on [replacing the hard drives in the Mac](https://www.lifewire.com/install-internal-hard-drive-mac-pro-2260171), you may find that SATA drives are offered in larger sizes and sometimes at lower costs than PATA drives. You can add SATA controllers to desktop Macs that have expansion buses.
-   **External Hard Drives**: Externals are a good choice as well, for both desktop and laptop Macs. For laptops, you can gain a performance boost by adding a 7200RPM external drive. External drives are also easy to add to a desktop Mac, and have the added benefit of removing a heat source from the interior of the Mac. Heat is one of the prime enemies of servers that run 24/7.

## External Connections

If you decide to use external hard drives, consider how you will make the connection. From slowest to fastest, here are the connection types you can use:

-   [FireWire 400](https://www.lifewire.com/what-is-firewire-2625918)
-   FireWire 800
-   [eSATA](https://www.lifewire.com/external-sata-esata-833450)
-   [USB](https://www.lifewire.com/what-is-usb-3-2260191)
-   [Thunderbolt](https://www.lifewire.com/what-is-thunderbolt-832713)

## Using macOS as a File Server: Installing the OS

Now that you have chosen a Mac to use, and have decided on the hard drive configuration, it’s time to install macOS (or OS X). If the Mac you intend to use as a file server already has the OS installed, you may think you’re ready to go, but there are a few things to consider that may convince you to perform a fresh install.

If you’re repurposing a Mac that already has the OS installed, chances are the startup disk has a great deal of unneeded data stored on it in the form of applications and user data that the file server won’t need. In our example, a repurposed G4 had 184 GB of data on the startup drive. After a fresh install of OS X, plus a few utilities and applications needed for the server, the amount of disk space already in use was less than 16 GB.

A fresh install lets you erase and test your hard drive. Unless they’re new drives, the hard drives will be operating for longer periods of time than they’re used to. It’s a good idea to use the "[Zero Out Data](https://www.lifewire.com/format-mac-drives-using-disk-utility-2260076)" security option to erase the hard drives. This option not only erases all of the data, but also checks the hard drive, and maps out any bad sections so they can’t be used.

While it’s true that OS X has built-in methods for keeping a disk from becoming heavily [fragmented](https://www.lifewire.com/need-to-defragment-mac-hard-drive-2260194), it’s better to start with a fresh install to ensure the system can easily optimize system files for their new use as a file server.

## Using macOS as a File Server: Configuring File Sharing

With macOS (or OS X) freshly installed on the Mac you will be using as your file server, it's time to configure the file sharing options.

## Setting Up File Sharing

[File sharing in macOS](https://www.lifewire.com/set-up-macs-file-sharing-options-2260207) is easy. Here are some of the settings and configurations to consider when using an old Mac as a server:

-   **Enable file sharing.** You will be using Apple's built-in file-sharing protocol, aptly named AFP (Apple Filing Protocol). AFP will allow Macs on your network to access the file server, and read and write files to and from the server, while seeing it as just another folder or hard drive.
-   **Select folders or hard drives to share.** You can select entire drives, drive partitions, or folders you wish others to be able to access.
-   **Define access rights.** You can define not only who can access any of the shared items, but what rights they have. For instance, you can give some users read-only access, letting them view documents but not make any changes to them. You can provide write access, which allows users to create new files as well as edit existing files. You can also create a drop-box, a folder that a user can drop a file into, without being able to see any of the folder's contents.
-   **Energy Saver**: If you’re going to run your server 24/7, you want to ensure that your Mac will restart automatically if there’s a power outage or your UPS runs out of battery time. Either way, 24/7 or not, you can [use the Energy Saver preferences pane](https://www.lifewire.com/use-energy-saver-preferences-pane-2260733) to configure your server as needed.

## Using macOS as a File Server: Energy Saver

How you run your file server is up to you. Most people never turn the server off once it's initiated, running it 24/7 so every Mac on the network can access the server at any time.

If you use your network for a home or small business, you may only want to turn the server on while you're working. If it’s a home network, you may not want all family members to have late-night access. In both of these examples, creating a schedule that turns the server on and off at preset times may be a good idea. This has the advantage of saving you a bit on your electric bill, as well as reducing heat buildup.

Thanks for letting us know!

Get the Latest Tech News Delivered Every Day

[Subscribe](https://www.lifewire.com/using-os-x-as-file-server-for-network-2260170#)
