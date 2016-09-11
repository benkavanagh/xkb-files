# Summary 
These are my xkb customisations. 

# Sources
The material here was derived from a number of great sources.

I learned about XKB at these locations:
 * https://wiki.archlinux.org/index.php/Keyboard_configuration_in_Xorg
 * https://wiki.archlinux.org/index.php/X_KeyBoard_extension  (best reference)
     setxkbmap -print -verbose 10
 * https://www.x.org/archive/X11R7.5/doc/input/XKB-Config.html
 * http://domwatson.codes/2014/11/who-needs-capslock-anyway-part-2.html
 * https://help.ubuntu.com/community/Custom%20keyboard%20layout%20definitions?action=show&redirect=Howto%3A+Custom+keyboard+layout+definitions
 * http://www.blaenkdenum.com/posts/custom-xkb-options-with-gnome/
 * http://unix.stackexchange.com/questions/90089/remapping-both-caps-lock-and-shiftcaps-lock-in-xkb


# Strategy

The summary of my strategy is as follows
  1. create an explicit keymap which includes my customised symbol definitions 
  2. compile and load my keymap with my local include directories so I don't need to modify the system area.
  3. create autostart desktop application that gets called when I login.
      
I decided on my final customisation strategy after reading this
 *  http://madduck.net/docs/extending-xkb/

# Contents of directories

The sub-directories are described below

* **applications**

   contains example application files to be put in .config/autostart

* **bin**

   contains shell commands that the desktop applications use to compile and install the keyboard map. 

* **keymaps**

   contains the keymaps for customised keyboard settings.  These are created by editing original keymap
   found from "setxkbmap -print" to add customised symbol definitions

* **symbols**

   contains the key remapping symbol definitions that are the critical part of the configuration. 


# Autostart

To configure keyboard on startup (Gnome, Linux) I add an application to .config/autostart

I decided that this was the best strategy based on these sources

* https://wiki.archlinux.org/index.php/Desktop_entries#Autostart
* https://ask.fedoraproject.org/en/question/59485/fedora-21-doesnt-come-with-gnome-session-properties/
