# Pimp My Kali *Autopilot*
This is [pimpmykali.sh](https://github.com/Dewalt-arch/pimpmykali/tree/master) made by [Dewalt](https://github.com/Dewalt-arch) and improved by me for auto install on virtual machines!

## The Problem:
- pimpmykali requires input from the user at at least 2 stages of **the first install of pmk on a virtual machine**.
- In trying to make a VirtualBox lab for doing Hack the Box and studying for the [PNPT](https://certifications.tcm-sec.com/pnpt/) I decided to use [Vagrant](https://developer.hashicorp.com/vagrant/tutorials/getting-started/getting-started-index).
- Vagrant automates making VMs, but pimpmykali requires keyboard input, **LAME!**

## How to Use:
If you want pimpmykali on your **NEW** VM, but don't want to wait to put in your options,
just clone this repo, use it exactly like you would [Dewalt's version](https://github.com/Dewalt-arch/pimpmykali/tree/master) BUT NOW you can 
automate setting up a new VM (`N` menu option in the OG version) in the following ways:
### Giving pimpmykali a flag:
Start pmk using either the `--auto` or `--auto-root` options:
- `./pimpmykali.sh --auto` Will run the `N` (OG) option and choose **NOT** to enable root user in kali
- `./pimpmykal.sh --auto-root` Will do the same but **WILL ENABLE** root user in kali

### Via the Options Menu:
If you didn't give pmk a flag at execution, you'll see the options menu.
From here you can still automate your VM install by choosing either `#` or `#R`
- `#` Will do everything the `N` (OG) option does but will **NOT** enable root user in kali
- `#R` Will do everything the `N` option does but **WILL ENABLE** root user in kali

## Enjoy!

:------------------------------------------- START OG README.md -------------------------------------------:

# pimpmykali.sh

[![pmk132tkab.png](https://i.postimg.cc/Qd9VCRrd/pmk132tkab.png)](https://postimg.cc/18SyY7tk)

# Fixes for new imported Kali Linux virtual machines
  - Author assumes zero liability for any data loss or misuse of pimpmykali
  - Can be used on a bare metal machines, but thats on you
  - Menu breakdown added below revision history

# Github index updated added +x permission:
  - Script is now be executable upon clone (perms: 755 rwxr-xr-x added to github)
  - There is no need to chmod +x pimpmykali.sh upon git clone

# Installation script:
  - rm -rf pimpmykali/
  - git clone https://github.com/Dewalt-arch/pimpmykali
  - cd pimpmykali
  - sudo ./pimpmykali.sh
  - For a new kali vm, run menu option N

# Special Thanks to Pimpmykali-Mirrors Testers!!
  - Crazy_Man - https://github.com/The-Crazy-Man
  - Andro

# Code Contributors
  - Yaseen - https://github.com/AhamedYaseen03
  - Crazy_Man - https://github.com/The-Crazy-Man
  - blindpentester https://github.com/blindpentester
  - pswalia2u https://github.com/pswalia2u
  - Alek https://github.com/wodensec
  - Gr1mmie https://github.com/Gr1mmie
  - Aksheet https://github.com/Aksheet10
  - 0xC0FFEE VirtualBox Home Lab Build (updated link!)
    https://benheater.com/building-a-security-lab-in-virtualbox/
  - TheMadHuman https://github.com/TMH-Sec
  - Aashiksamuel https://github.com/aashiksamuel  (sublime install fix)
  - m4ul3r 

# Writeups / Honorable Mentions
  - ip3c4c_n00b https://ip3c4c.com/2202_homelab_vmware/

# Revision 1.7.0 - MobSF
  - MAPT Course setup, Menu option A 
   - mobsf installation has been changed to a docker installation
   - /usr/bin/mobsf-docker script created and made executable 
  
# Revision 1.6.9a - changed google-chrome installation source
  - is now installed from the kali repo google-chrome-stable 

# Revision 1.6.9 - fix_impacket restored
  - menu options N, 0 and 1 are fully operational   

# Revision 1.6.8 - fix_impacket function temporarily commented out
  - affecting menu options N, 0 and 1 
  - issues with kali2023.2 

# Revision 1.6.7 - Added installer and Uninstaller for Nessus
  - menu option @ to install nessus
  - menu option $ to nuke nessus 

# Revision 1.6.6 - Hacking API Course setup 
  - added Practical API Hacking Course setup (amd64 and arm64), menu option O
  - Instructor Alex Olsen https://academy.tcm-sec.com/p/hacking-apis
  - menu options rearranged in stand alone functions

# Revision 1.6.5 - impacket
  - added --user to impacket 0.9.19 install

# Revision 1.6.4 - minor code cleanup 

# Revision 1.6.3 - mitm6 installation
  - mitm6 moved from a python2 to python3 installation
  - added --breaks-system-packages to get around pip related issues 
  - liblibc symlink correction added at the end of this function
  
# Revision 1.6.2 - FixSSH Removed
  - use kali-tweaks 2023.1.3 to resolve the issue with ssh -i and hydra out of memory

# Revision 1.6.1 - $pyver variable
  - removed single quotes

# Revision 1.6.0 - Atom removed + misc fixes/updates
  - Corrected the non-interactive shell being opened for:
    - Menu option K - Reconfigure Keyboard 
    - Menu option T - Reconfigure Timezone
    - shell is now interactive and functions properly

  - Added $archtype variable for potential upcoming arm64 specific support ( Mac m1, rasberry pi, etc )
  - Added $pyver variable for detection of version of python3
    - corrects error with installing python'$pyver'-venv and other various python required installations

  - Atom 
    - has been deprecated/sunset and the installation of atom has been removed
    - menu option 7 - Install atom removed 

  - Seclists
    - changed seclists to be pulled from github, to be more verbose about what is taking place on screen

  - gowitness function updated to detect amd64 or arm64 installations, still installs from github

  - httprobe, assetfinder, amass are now installed from the kali repo instead of github

  - Misc Fixes 
    - corrected if statement on line 1240 MPP Course Setup
    - added function for apt_fixbroken and apt_fixbroken_complete
    - removed functions: fix_bloodhound, ask_python39, fix_python39, fix_resopnder 
    - addded -o Dpkg::Progress-Fancy="1" to all apt operations for fancy progress bars
    - moved virt-what to be installed much earlier in the script 
    - general code cleanup

  - Menu option B restored to BlindPenTesters - TheEssentials
  - older revision history moved to changelog.txt  

# Menu Breakdown of Pimpmykali

- Menu option N  (New Users/New VM's Should start here!)
  - executes menu option 0 fix all ( options 1 thru 8 )
  - executes menu opiion 9 (pimpmyupgrade)


- Menu option = Pimpmykali-Mirrors (rev 1.3.2)
  - obtain kali mirror list and process
    - round-trip-time ping test to all mirrors, select top 10 with shortest rtt
    - small download >1MB from the top 10 mirrors, select top 5 fastest transfers
    - large download 10MB test the final 5 mirrors, select fastest transfer
    - generate new /etc/apt/sources.list with the new selected mirror
    - prompt Y or N to write new changes to /etc/apt/sources.list
      - Y writes changes /etc/apt/sources.list
      - create backup of original sources.list in /etc/apt/sources.list_date_time
      - write new deb and deb-src lines with new mirror to /etc/apt/sources.list
      - N exits and makes no change to /etc/apt/sources.list


- Menu Option ! - Nuke Impacket (yes its literally the ! character)
  - removes any prior installation of impacket (gracefully and forcefully)
  - installs impacket-0.9.19


- Menu Option 1 - Fix missing
  - fix_sources
    - uncomment #deb-src from /etc/apt/sources.list
  - python-pip installation via curl
  - python3-pip installed
  - seclists installed
  - gedit installed (feature request)
  - flameshot installed (feature request)
  - locate installed (feature request)
  - fix_rockyou function
    - gunzip /usr/share/wordlists/rockyou.gz to /usr/share/wordlists/rockyou.txt
  - fix_golang function
    - installs golang
    - adds golang GOPATH to .bashrc and .zshrc
  - installs htop
  - installs python requests
  - installs python xlrd==1.2.0
  - disables xfce power management
  - blacklists pcspkr kernel module /etc/modprobe.d/nobeep.conf
  - intalls python pyftpdlib


- Menu Option 2 - Fix smb.conf
  - adds below [global] in /etc/samba/smb.conf
    - client min protocol = CORE  below [global]
    - client max protocol = SMB3  below [global]


- Menu Option 3 - Fix Golang 
  - Installs golang
    - checks for GOPATH in .bashrc and .zshrc
    - if GOPATH is found, adds nothing
    - if not found, adds GOPATH statements to both .zshrc and .bashrc


- Menu Option 4 - Fix Grub
  - adds mitigations=off to GRUB_CMDLINE_LINUX_DEFAULT


- Menu Option 5
  - installs Impacket-0.9.19


- Menu Option 6 - Enable root login
  - installs kali-root-login
    - prompts for root password
    - copy /home/kali/* to /root prompt (1.1.2)
    - prompt are you sure? to copy /home/kali to /root prompt (1.1.3)


- Menu Option 7
  - removed from the menu 


- Menu Option 8 - Fix Nmap
  - wget nmap script fixes
    - clamav-exec.nse
    - http-shellshock.nse (Thank you Alek!)


- Menu Option 9 - Pimpmyupgrade
  - additional notes will be added
  - fix : Hypervisor detection (vmware, virtualbox, qemu/libvirt)
    - add additional details here
  - fix : virtualbox shared folder fix applied     


- Menu Option 0 - Fix all (1-8)
  - Executes ONLY Menu options 1 thru 8


- Menu Option B  ( Changed 01.15.2023 )  
  Previous Function: (will be moved elsewhere in Pimpmykali)
  - BlindPentesters The_Essentials tools and utilities collection
  - Install all of BlindPentesters favorite tools and utilities to /opt (aprox 8GB)
  - Click the link below for a full list of the_essentials.sh script and its inner workings
  - https://github.com/blindpentester/the-essentials


- Menu Option C
  - Install Google-Chrome


- Menu Option F
  - Fixes XFCE Broken Icons "TerminalEmulator" Not Found
  - Fixes XFCE Open Catfish instead of Thunar when double clicking Home or FileSystem Icon
  - this fix is a temporary fix and will be removed once xfce has been corrected


- Menu Option G
  - Apply gedit unable to open display as root fix


- Menu Option K
  - Reconfigure Keyboard, Language and Layout + Variant


- Menu Option M
  - Kali linux setup for Mayors Movement Pivoting and Persistance Course
    - installs covenant  


- Menu Option O - Practical API Hacking Course
  - Practical API Hacking course setup 
  - amd64 and arm64 aware
  - root user and normal user aware
  - installs docker.io docker-compose
   - docker service is enabled 
  - installs postman to /opt/Postman/Postman 
   - symlink is created for /opt/Postman/Postman at /usr/bin/postman
  - cleanup.sh script created 
  - installs crAPI to $HOME/labs
  

- Disable Power Management function moved to Menu options 0, N or 1
  - Based upon detection disable power management for that environment
    - Detect desktop environment
      - XFCE
      - Gnome


- Menu Option S - Fix Spike
    - Fixes undefined symbol error thrown when using generic_send_tcp
    - this fix is temporary and will be removed once a corrected version is available


- Menu Option T
  - Reconfigure Timezone


- Menu Option V
  - Install MS VSCode


- Menu Option W
  - Install GoWitness precompiled binary


# TODO   
  - clean up todo list :)
