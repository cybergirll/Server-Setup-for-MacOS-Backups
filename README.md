# Server-Setup-for-MacOS-Backups
JStreet Assessment
## Creating a Server
#### Setting up a Virtual Environment

*I am going to set up Linux-based server environment for this task. It has preinstalled security configurations and it is developer friendly with Python, Docker and web-development tools pre installed*.

### A written explanation on how to set up the server with code snippets and configurations.
*Documentation outlining the steps taken and challenges faced and also suggestions for future enhancements*.
#### We can use a method of installing VM either with Docker container or a VirtualBox. I am going to demo this use case with VirtualBox hypervisor.

- Download [VirtualBox]( https://www.virtualbox.org/)
- Save the file.
#### Install VirtualBox

- Run the installer once the download is finished.
- Answer Yes to the Windows UAC prompt (check for flashing icon in your taskbar)
- Select Finish.

#### VirtualBox Extension Pack

- Download the [VirtualBox Extension Pack](https://www.virtualbox.org/wiki/Downloads)
- Click the link that says "All supported platforms" under the Extension Pack section.
- Save the file.
- Install the VirtualBox Extension Pack.
- Open the Extension Pack file you just downloaded.
- Agree to the terms by bringing the scroll bar down and clicking "I Agree".
- Answer Yes to the Windows UAC prompt (check for a flashing icon in your taskbar).
- Click OK after it successfully installs.

### Kali Linux Installation

*Since many enterprise backup solutions run on Linux - Kali would be an excellent server that uses Debian Linux based image with better resource efficiency rather than Windows*.

#### Initial Setup

- Download the latest [Kali ISO Image](https://www.kali.org/downloads/).
- Download the image in the first row column. It's 3GB+ and may take a while depending on network speed.

*Create a new Virtual Machine (VM)*

- Open VirtualBox and create a New VM.
- Name it as *you wish*, set the Type to Linux and Version to Debian, as Kali is a derivative.
- Choose a memory size (powers of 2). We recommend allocating a quarter of your total system memory e.g. if you computer has 8G then set it to 2048 MB. If memory is scarce then stick with 1024 MB. You may be able to get by with less but performance will be heavily impacted due to swapping/paging to disk.
- Create a virtual hard disk, of type VDI, dynamically allocated with AT LEAST 25GB of space. If you have plenty of free space we recommend 50GB.

  | *Note*                 | *Description* |
  | --- | ---|
  | When creating new VM | Be cognizant of your host operating system's memory needs |
  | When creating a Virtual hard disk | You can always grow (but not shrink) the drive's capacity, partitions and filesystems later |
                                     
### Mounting the ISO and Bootstrapping

- After creating the virtual hard drive you will be back at the main VirtualBox Manager window. From here, make sure the new Kali VM is highlighted blue and click the green arrow Start button.
- Next you'll be prompted for a start-up disk. Click the little folder icon with the green arrow.
- Add a new virtual optical disk image (ISO) file.
- Open the ISO you downloaded previously in your Downloads folder. Then click Choose.
- click Start.

### Kali Installation

*Configuring the Locale and Hostname*

- Once the installer boots up, choose Graphical Install and press Return/Enter.
- Next choose your language, location and keyboard layout.
- After a few minutes of loading you will be asked for a hostname. For the purposes of this course you can set this to what you want as long as it is a single lowercase word or you can just leave the default as kali.
- Leave Domain name blank. If you were making the VM a publicly accessible server and linking it to a DNS record, you would use its fully qualified domain name e.g. kali.example.com.

*Creating a User and Setting a Password*

- When setting up your user account, the Full name is your "display" name while the Username for your account is the actual login username. Set your username and password to something you'll remember.
- *WARNING: Usernames in Linux are case-senstive*. When logging in, you must type them exactly as you created them. It may be easier for you (and others) to remember if you follow the standard convention of keeping usernames all lowercase.

*Timezone, Partitioning, Filesystem layout*

- Set your timezone.
- Go with the default partition layout of Guided - use entire disk.
- Click continue to partition your only virtual disk: sda. Note how Linux names its drives. The first SCSI (or SATA) disk attached is named sda. If you attached a second one, it would be named sdb, third would be sdc and so forth.
- Choose All files in one partition in order to keep the partitioning layout simple. This will make it easier to enlarge the disk and filesystem later on should the need arise.
- Select Finish pertaining and write changes to disk and continue.
- confirm Yes and continue in order to make the changes take effect. Your final layout has 2 partitions, 1 partition for files and 1 for swap. Swap is used as a sort of RAM backup when the system runs out of memory and needs to write to the hard drive. When a system runs out of RAM it'll bring the system to a crawl. Small amounts of swap space is also used regularly for instance, whenever a low priority process has been asleep for some time and no longer requires high-performance RAM.

*Software Installation*

- Once the base system is installed you'll be asked for proxy information. Leave the field blank (default).
- Next you'll choose which extra software to install. Go with the default Xfce Desktop environment or choose another. GNOME was the default in the last edition of Kali (pre-2020). You can also choose multiple environments to try out, but keep in mind that adding more will use more space on the hard drive. Each one consumes roughly 1G.
- Leave Collection of tools at the default setting and continue.

*Bootloader Install and Reboot*

- Towards the end, you'll be asked to Install the GRUB (GRand Unified Bootloader) to the master boot record (MBR). Mark Yes, continue and choose /dev/sda to finish the final installation process.
- **the installation is complete!** 

