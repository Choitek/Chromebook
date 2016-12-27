Installing Arduino, OSC, Python on the chromebook
-------------------------------------------------

SOURCES: http://lifehacker.com/how-to-install-linux-on-a-chromebook-and-unlock-its-ful-509039343
http://www.howtogeek.com/210817/how-to-enable-developer-mode-on-your-chromebook/ 
https://liliputing.com/2014/06/asus-c200-chromebook-enabling-dev-mode-installing-ubuntu.html 
http://playground.arduino.cc/Linux/Ubuntu 

PART 1: Put chromebook into developer mode
------------------------------------------

WARNING: This will wipe your local data (not that chromebooks can hold much data).  It will also violate the warranty

 1. Put your chromebook into recovery mode: Press and hold the Esc and Refresh keys, then press the Power button (while still holding the other two keys).   
![recovery image](http://www.howtogeek.com/wp-content/uploads/2015/02/ximg_54f133d38a2aa.jpg.pagespeed.gp+jp+jw+pj+js+rj+rp+rw+ri+cp+md.ic.8LhjjiOeKf.jpg)
 2. When you see the yellow exclamation point—press *Ctrl+D*. This will bring up a prompt asking if you want to turn on Developer Mode.  (The *Ctrl+D* command is not shown on the screen.  Google intentionally hid this feature to prevent people who didn’t know what they’re doing from destroying their chromebooks)
![recovery image](http://www.howtogeek.com/wp-content/uploads/2015/02/ximg_54f13d35ab77f.jpg.pagespeed.gp+jp+jw+pj+js+rj+rp+rw+ri+cp+md.ic.IlM36weNir.jpg)
 3. Press enter to continue.
 4. The laptop will start do various things, including restarting several times while beeping obnoxiously.  DO NOT TOUCH IT.  This will take about 10 minutes.
 5. When you see the welcome page, now you can start touching it.  Set up your account.

Note: whenever you turn on your chromebook, you will get a message saying that the chromebook is in developer mode.  Just wait until the screen goes away, or press *Ctrl-D*.

![enter image description here](http://www.howtogeek.com/wp-content/uploads/2015/02/ximg_54f13e9a6f60f.jpg.pagespeed.gp+jp+jw+pj+js+rj+rp+rw+ri+cp+md.ic.9D9nY51pCC.jpg)

**PART 1 - ERROR) The ESC-REFRESH-POWER** command isn’t working! Some older Chromebooks have a physical switch that activates Developer Mode.
**PART 1 - REVERSE)**  If you ever wish to reset your chromebook (and get out of developer mode)
Restart your computer to bring up this screen

Hit spacebar followed by enter will get you out of developer mode (and delete everything)

PART 2) Install Crouton
-----------------------

 1. Download Crouton by clicking on the link here >>>>http://goo.gl/fd3zc<<<< and save it in your Downloads folder (when you download the file chrome os will save it in the downloads folder by default).
 2. Press *Ctrl+Alt+T* to open crosh (chrome’s terminal)
 3. At the Terminal, run the following command to enter a Ubuntu shell: (for those who don’t know how to use terminal, just type in the text below exactly and hit enter).  If you get an error at this step (“the shell command does not exist” it means your chromebook is not in developer mode.  Go do Part 1.)
**shell**
Next, run the command corresponding to your machine to install Crouton:

MOST CHROMEBOOKS: 

    sudo sh -e ~/Downloads/crouton -t xfce

John Choi’s C202s: 

    sudo sh -e ~/Downloads/crouton -t lxde

![enter image description here](/pictures/install.png)

 4. Wait about 20 min

NOTE: this step may fail (several times) due to faulty internet or other issues.  Just retry the command until you it asks you for your username
Follow the prompts to set up your account (type in your desired username once and then type in your desired password twice when it asks for that information)

![enter image description here](/pictures/username.png)

PART 2 - PRACTICE) familiarize yourself with chronos
---------------------------------------------------------------
**(optional)**

 1. Close the terminal (tab) by hitting the X button
 2. Open it again using *Ctrl+Alt+T*

PART 3) Start up Ubuntu
-----------------------

 1. After it's finished installing, run the commands corresponding to your machine to start your new desktop environment:

Most chromebooks

    shell
    sudo startxfce4

John Choi’s C202s

    shell
    sudo startlxde

![enter image description here](/pictures/ubuntu.png)

**PART 3 - ERROR)** OMG I get a scary error message (d-bus) when I try to start ubuntu!
For some reason John Choi’s Asus C202s can’t handle the default mode of ubuntu that everyone likes.  If you get a “d-bus” error, try installing ubuntu in “lxde” mode instead of “xfce” mode.

 1. Do PART 1- REVERSE) to clean your hard drive
 2. Redo PART 1)
 3. Then do steps 2 and 3 again, but follow the instructions specific to the Asus C202s

PART 3.5) Getting familiar with the interface (optional)
--------------------------------------------------------

 1. Go back to chrome os and linux using the following keyboard-shortcuts (back and forward keys DO NOT refer to the left/right keys, but rather the left arrow and forward arrow keys you will find at the top of the keyboard)
ARM processors (including John Choi’s Asus C202s)
Intel processors
*Ctrl+Alt+Shift+Back* to go to chrome os
*Ctrl+Alt+Shift+Forward* to go to ubuntu
*Ctrl+Alt+Back* to go to chrome os
*Ctrl+Alt+Forward* to go to ubuntu
*Ctrl+Alt+Refresh* to bring up the desktop (only for intel processors)

![enter image description here](http://cdn2.expertreviews.co.uk/sites/expertreviews/files/2015/08/switch_to_chroot_keys.png?itok=SW6pp_Ha)

 2. Exit the Linux desktop by logging out of it like you would on a normal PC—you'll close it completely and go back to Chrome OS
 3. Use “sudo startxfce4” (or “sudo startlxde”) again to log back in.

Note: 
-Many Ubuntu tools are left out, so you’ll have to install them yourself.  Not all apps will be compatible.
-XFCE’s screensaver cause graphics issues in Chrome OS and may need to be disabled
-The Downloads folder in Chrome OS is the same as the Downloads folder on the Linux desktop, so if you download or create a file in one environment, you can put it in the Downloads folder to make it available in the other as well.

PART 4-SHORT) Installing things (short version)
-----------------------------------------------

 1. Open up chronos (Ctrl-Alt-T)
 2. Open ubuntu

      **shell**
      **sudo startlxde**

 3. Open terminal 
 ![enter image description here](/pictures/terminal.jpg)
 4. Install lots of things

    **sudo apt-get install arduino arduino-core python2.7 python3 default-jre default-jdk python-pip python-serial**

 ![enter image description here](/pictures/command.jpg)

 4. Enter the following to install python OSC drivers (no need to enter password or type “y”)

    **sudo pip install python-osc**

Note: you may need to type in “sudo” (when using command line) or select “run as administrator” (when using graphic user interface) when running various programs, including arduino to give the software full permissions.

**PART 4-SHORT-ERROR)** if the above commands do not work, install things individually by following the instructions below


PART 4.1) Installing arduino
----------------------------

 1. Open ubuntu
 2. Open up terminal in whatever version of ubuntu you installed (it will be in the start menu) and type in the following: (ensure you have internet access)

    **sudo apt-get install arduino arduino-core**

 3. Type in the following to open arduino (the “sudo” gives you write access to the serial ports)

    **sudo arduino**

**PART 4.1 - ERROR)** You get an error saying that you need to be added to a “dailout” list and that you need to logging out and logging back in so you can upload code to an arduino.  Then, you will be unable to access the serial ports.  
If you get this error, ensure you typed in “sudo” at the front of your command.
(Hitting “add” and then logging out and logging back in doesn’t fix the problem, although if the problem persists then there’s no harm in trying it anyways.)

**PART 4.1 - ERROR)** Permission denied.  You can open up arduino, and see the serial ports, but you can’t upload code. 
This may happen if you try to install arduino normally using the GUI.  Installing using the GUI prevents you from using “sudo” when you open it, meaning you will not have permissions.

PART 4.2) Installing python and other developer package
-------------------------------------------------------

Note:
-Ubuntu comes installed with both python 2.7, python 3.5 and the java runtime environment (but not the java development package.)

 1. Open ubuntu
 2. Open the terminal
 2. Enter the command specific to what you want to do

Terminal python: **sudo apt-get install python2.7 python3**
Manual python: https://www.python.org/downloads/source/
Java: **sudo apt-get install default-jre default-jdk**

**STEP 4.2 - ERROR)** Try running your program with sudo.

STEP 4.3) Install OSC (Open Sound Control) Python Plugin
--------------------------------------------------------

 1. Open ubuntu
 2. Install pip

    **sudo apt-get install python-pip**

 3. Install Open Sound Control

    **sudo pip install python-osc**

STEP 4.4) Install Pyserial
--------------------------

 1. Open ubuntu
 2. Install pyserial
Python 2.7: **sudo apt-get install python-serial**
Python 3.5: **sudo apt-get install python3-serial**


STEP 5) Serial on chrome OS (native)
------------------------------------------------------------------------

 1. Install from link below
https://chrome.google.com/webstore/detail/arduino-chrome-serial-mon/opgcocnebgmkhcafcclmgfldjhlnacjd?hl=en

STEP 6) Python on chrome OS (native)
------------------------------------

 1. Go to https://repl.it/languages/python 
 2. Enjoy

Note: This method is highly restrictive because it does not have access to your drivers and the like.  Thus, if you want to use pyserial, you will need to do it on ubuntu.
