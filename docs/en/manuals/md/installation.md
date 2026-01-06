# Installation (Full Manual)

> Source PDF: [INSTALL_ENG.pdf](../pdf/INSTALL_ENG.pdf)

## Page 1

### On Premise Srt Server Setup

Once you have selected the computer to install the OnPremise SRT Server system, have in mind that all the information in its hard-drive will be completely erased and replaced by the

new system. IT WON’T WORK ON A VIRTUAL MACHINE, ONLY BARE METAL.

### Steps to follow

1.- Download the ISO file zipped, and decompress it into a folder. 2.- You can record the ISO content into a optical disk or into an erasable USB drive. The ISO content is less than 500 MB, so it should fit on any bigger storing media.

a) Optical disk. You can use BurnAware or any other, and select “Record ISO” b) USB drive. You can use Rufus v3.13 or above. Once USB is plugged in, press Select button, choose the ISO file and Press Start.

Choose Write in DD Image mode, and accept the warning of data destroyed. Once recorded, the GREEN status bar will show the message “READY”. You can unplug the USB

drive and we are ready to start the setup.


## Page 2

3.- First of all, you will have to enter the BIOS of the target computer, to change the boot order, so the ISO image is booted first of all.

### 4.- When the ISO image boots, you will see the following menu

The left one, when booting from an optical drive, and the right one when booting from an USB drive (Rufus adds extra menu items). We will ALWAYS select Install and press the ENTER key

### Select your language, location and keyboard configuration

The installation procedure will start. Write a descriptive name for your computer in Hostname, and you may bypass the Domain name if you don’t have an internal DNS server in your local network.

Select your timezone too. If the hard-drive in the target machine is not empty, you will reach to this screen:


## Page 3

You will Go back, and select Detect Disk and press the ENTER key. Then select any of the “use entire disk” you want. And choose the target computer’s hard-drive (the second one is the USB drive)

The installation will continue, until question “Scan another CD or DVD?”, we say NO. Finally if you are asked when to install the boot loader, choose the target hard-drive.


## Page 4

The latest installation screen will appear. Continue and we are done. The target computer will reboot and will show a big BLUE square in the screen. Wait until the

process ends in a black screen with login prompt. The system will be configuring more internal stuff, and will reboot again in less than 1 minute. After this second reboot, wait until the black

screen with the login prompt appears again with hostname you chose. The installation procedure has finished. It’s time to enter the dashboard. Your OnPremise SRT Server system will be accesible from any LAN computer thru a browser, but

we will need to detect its IP. You can use Bonjour Browser (http://hobbyistsoftware.com/bonjourbrowser) for this quick task.


## Page 5

Enter the IP address found (in this example is 192.168.1.24:80, and you can bypass the :80 of the HTTP protocol that your browser already knows) Username: admin Password: admin (for the admin’s role)

Username: user Password: user (for the user’s role) Don’t forget to change your passwords for security, and also set your recover e-mail. Now you can start playing with your new OnPremise SRT Server system.

Have a nice time !!! IMPORTANT: Before working, go to the License tab and ensure your device has connected to our licenses server and got a LICA-G free license for the next 30 days. If not, your new channels will

only work for 5 minutes and no more. Enter a valid DNS in the Network tab, to ensure the connection with the license server, and the download of a new keyword for the next 7 days. Do not

disconnect your server from the Internet more than 7 days or will also get locked. 2020 TodoStreaming
