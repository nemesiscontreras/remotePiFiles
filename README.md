# Editing Files on the Pi Remotely from your laptop using Atom text editor

This tutorial will guide you through opening up the files from your Pi so you can easily write code from your laptop as oppose to trying to edit code via the terminal.You can also use SSH pr VNC but once you want to edit or write large chunks of code I suggest giving this a try!
 The  steps  are based on this write up:


[Link to write-up ](https://github.com/pubnub/workshop-raspberrypi/blob/master/SSHFS%2BMacFUSE.md)


*Note this only works for MAC but if you are a Windows user etc and know of an alternative to reach the same goal post up the tutorial!*

1) Download Atom text editor from : https://atom.io/ also know as the “21st Century hackable text editor”

2) Know the IP Address of your Pi (usually you can find it by typing Hostname -I on the Terminal of the Pi or via SSH)

3) Download 2 programs SSHFS and FUSE for OS X [from this link](https://osxfuse.github.io/).  Make sure to double click the programs once they have downloaded to run through the installation process for both of them

4) On your laptop create a folder in the location you want the Pi’s files to be. I created my folder under Documents. It is recommended that you name the folder “Mount” to follow the instructions will less fuss but feel free to rebel.

5) Open Terminal from your laptop and type :

**sshfs pi@PiIPAddress:// ~/Documents/Mount -ovolname= Mount**

explanation:
 pi@PiIPAddress : gives the IP Address of your Pi
~/Documents/Mount : is the location of where we out the folder named Mount
-ovolname= Mount : this gives the name Mount to your folder (otherwise a weird name shows up)

6) *If you encounter an error* I suggest going over to the terminal to check the exact location on where you created your Mount folder:  type ls -a this will list all the folders you have.  Navigate to the folder where you put the Mount folder (in my case it was Documents) so type: cd Documents the type ls again and confirm there is a Mount (in our case there is!)

7) You should then be asked for your Raspberry Pi Password which is raspberry by default unless you changed it, type it in !

8) Now if you navigate back to the Mount folder you will see it will have little people on it as well as an arrow next to it which means the raspberry Pi Files are accessible to us!

9) Next on your laptop open up Atom -the program we downloaded in step 1- then select File —> Open, then navigate to your Mount folder and select open !

10)You will now see all the folder’s on from your Pi’s Brain available to edit !

11) You can now view and edit all your Python scripts etc from the Atom Editor!

12) When you are done editing files (make sure you save your code) simply go back to the Mount Folder and click the black arrow. The little people will go away and the folder will turn blue. Close Atom and turn off your Pi
