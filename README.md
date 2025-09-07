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
  
