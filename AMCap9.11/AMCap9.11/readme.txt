--------------------------------------------------------------------------------

  AMCap - Version 9.11                                              README.TXT
  Copyright © 1997-2004, Microsoft Corporation                   December 2006
  Copyright © 2004-2006, Noël Danjou <webmaster@noeld.com>

--------------------------------------------------------------------------------


About AMCap
-----------

  AMCap is a small yet fully functional video capture application. 
  It is a program much like Microsoft VidCap but which adds support for
  DirectShow (formerly ActiveMovie, hence the name.) It is based on the sample
  AMCap source code from the Microsoft DirectX 9 SDK. This custom version adds 
  many new features including:

   - DV camcorder playback and recording
   - improved MPEG-2 playback and recording
   - improved analog TV tuner support
   - still capture in BMP, JPEG and PNG formats
   - optional real-time compression (Windows Media or any installed CODECs)
   - remember video input, standard, size and many other options from previous
     session
   - full screen mode
   - support for multi-monitor and deinterlacing (using VMR9)
   - caption bar and menu on/off
   - always on top feature


  The registered version includes a new stillcap application that allows you
  to easily make still captures from a script, an application, a command prompt, 
  the task scheduler, etc.
  


  Important note:

  GdiPlus.dll is required. On Windows 2000, 98 and ME, you need to
  install the redistributable file available at:
   http://www.microsoft.com/msdownload/platformsdk/sdkupdate/psdkredist.htm
   (click the GDI+ link)

  or

   http://www.microsoft.com/downloads/details.aspx?
       FamilyID=6a63ab9c-df12-4d41-933c-be590feaa05a&DisplayLang=en
   (copy and paste this link on a single line)        



Registration and redistribution
-------------------------------

  Even though this version of the program is fully functional, I beg you please 
  to register to show your support and your interest. Your support would allow
  me to add more features and to possibly fix bugs.

  To register click the "Help" > "AMCap on the web" menu then on the web page 
  click the green "Register Now" button and follow the instructions.

  Computer magazine publishers are welcome to redistribute the unregistered 
  version of the application on their complimentary or monthly CDs. Any other 
  redistribution of the application with commercial products is strictly forbidden
  without my written permission. Please contact me for a license agreement (see 
  "Contact details" at the end of this file.)



Notes about graphic cards with Video Ports (VP)
-----------------------------------------------
  
  - some features (Still capture and the VMR9/multi-monitor features) bypass
    the Video Port on such graphic cards so the rendering may be visibly slower
    than with the use of the fully accelerated VP. For better performances, use
    a graphic card compatible with DirectX 9 and VMR9.
  - graphic cards with a VP require the Video Port Manager filter (only
    available in Windows XP and later) to make still capture and the 
    VMR9/multi-monitor feature possible.



Command-line parameters
-----------------------

  /capture

    Automatically starts capturing video as soon as AMCap starts.
    (requires preconfiguration)


  /close

    Closes the application when the still capture is done or once the time-limit
    of the video capture is reached.


  /debug

    Registers the graph with the Running Object Table so that GraphEdit can
    connect to it.


  /fullscreen

    Starts AMCap in fullscreen mode


  /nocaption

    Starts AMCap without the caption and menu bars.


  /snap[:<delay>]
     
    Makes a still capture as soon as AMCap starts or after the optional delay 
    in milliseconds. (requires preconfiguration)


  /unregister

    Deregisters AMCap so that it does not accept STI events anymore.



Errors and solutions
--------------------

  * CreateGrabber: CoCreateInstance failed, hr=0x80040154

    Your version of DirectX is too old. Please upgrade to DirectX 9.0c or later.

  * Cannot render video capture stream, hr=0x80070057
    
    The selected video capture source may be in use by another application.



History
-------

  * December 4, 2006 - Version 9.11 (Build 109.4)

   - added "Remember camera controls" option to save and to restore camera information 
     like pan, tilt, zoom, exposure, etc.
   - added TV programs management (when an analog TV tuner is available)
   - fixed an issue that could lead to invalid values being displayed in some error 
     messages
   - added a manifest for Windows Vista's UAC support
   - added a digital signature to the executable
   - added "Still Capture Pin..." option to configure high resolution if a Still pin
     is available
   - added volume control and bargraph (VMR9 required)
   - added simultaneous MPEG-2 preview and capture
   - added support for Type-1 and Type-2 DV capture
   - added crosshair option due to numerous requests
   - fixed a bug that could prevent compressor property pages from showing in Setup >
     Compression tab
   - added support for some media and remote control keys
   - fixed menu bar on/off option always resizing the window to default size
   - fixed an issue that prevented the preview window to be shrinked to a size smaller
     than the default video resolution
   - fixed a possible crash when a still capture is requested and GDI+ is not installed
   - improved error reporting, you should get less "(error message unavailable)"
   - improved still capture, requires less configuration and possibly better 
     performances
   - improved overall MPEG-2 support, more tuners or capture cards should be supported
   - improved MPEG-2 capture so that no external dump filter is required
   - improved backward compatibility for capture sources with a video port
   - the cursor is now automatically hidden in fullscreen mode


  * June 21, 2006 - Version 9.10 (Build 88.3)

   - fixed TV channel selection not working
   - improved overall TV tuner management and support
   - improved DV camcorder support
   - improved capture file management, you're no more required to preallocate 
     a capture file anymore
   - added new Setup with tabs (Capture > Setup... menu). Setup now gives 
     access to some options that were only accessible from the Registry
   - added option to change OSD color
   - added TV Channel management
   - added TV audio menu
   - added audio input and crossbar audio input menus
   - added Synchro Start to start/stop DV camcorder playback at the same time
     as the capture in one click
   - added support for AVI compression and CODEC selection (experimental)
     (see Capture > Setup... > Compression tab)
   - added a new help file
   - fixed many bugs


  * March 2, 2006 - Version 9.08 (Build 75.3)

   - added an installer for easy installation and removal


  * February 15, 2006 - Version 9.08 (Build 75.3)

   - added a new option in Capture > Still menu to always save the still captures
     to the same file. Every capture will overwrite the same file instead of 
     creating a new timestamped file
   - added a new "Auto Switch Inputs" option in Options > Video Input menu. If
     the video device has more than 1 input, AMCap will automatically switch
     from one input to the next one every 10 seconds


  * January 4, 2006 - Version 9.08 (Build 70.3)

   - fixed: the window had a wrong aspect ratio after being minimized and then
     restored


  * December 13, 2005 - Version 9.08 (Build 68.2)

   - fixed the settings were not saved in some exit conditions
   - set both video capture and preview resolutions to the same size at startup
     if both are available. Previously only capture resolution was restored
   - implemented Demo version


  * November 17, 2005 - Version 9.08 (Build 65.4)

   - enhanced aspect ratio handling to avoid picture distorsion after resizing
   - added Options > Set Priority menu to boost the application priority in the 
     multithreading scheduler and to possibly get better performances


  * November 3, 2005 - Version 9.08 (Build 63.4)

   - reactivated the system menu from the taskbar button when the caption and the 
     menubar are hidden in the application
   - added on-screen display of TV channel (VMR9 required)


  * October 18, 2005 - Version 9.07 (Build 61.2)

   - added Window > Flip View menu
   - added +/- accelerators to quickly toggle between the video inputs


  * September 5, 2005 - Version 9.07 (Build 59.1)

   - added /capture command-line parameter
   - added save and restore feature for TV tuner input type (cable or antenna)
   - added Options > Pause menu, to pause or unpause the live preview
   - described supported command-line parameters


  * August 5, 2005 - Version 9.06 (Build 54.4)

   - added "/snap[:<delay>]" and "/close" parameters. /snap makes a still
     capture as soon as AMCap starts (if it was correctly preconfigured) or
     after the specified delay in milliseconds. /close closes the application
     when the still capture is done.


  * June 10, 2005 - Version 9.06 (Build 52.5)

   - fixed a memory leak
   - enhanced STI to DirectShow device lookup


  * May 17, 2005 - Version 9.06 (Build 50.2)

   - added "Register for STI events" menu under Capture. This option enables
     AMCap to appear in the list of applications in the Events tab of the 
     item properties in "Scanners and Cameras" 


  * May 4, 2005 - Version 9.06 (Build 49.3)

   - changed still image filenames to unique time-based filenames to avoid 
     overwriting
   - added a "Copy to clipboard" option in the Capture > Still menu. If ticked
     the Snap option copy the image to the clipboard instead of to the disk
   - remember and restore the selected audio input on entry and on exit


  * April 12, 2005 - Version 9.05 (Build 48.2)

   - added support for mouse wheel to change the TV channel


  * March 25, 2005 - Version 9.05 (Build 47.5)

   - added Remember > Image Controls menu to optionally save and restore 
     Brightness, Contrast, Hue, Saturation, Gamma, Sharpness, WhiteBalance, 
     and Gain.
   - the settings are now saved and loaded to/from an AMCap.ini file which
     must be placed in the same folder as AMCap.exe. This allows easy
     preconfiguration.
   - added a Capture > Still > Format menu to specify the format in which
     still images are saved. JPEG and PNG are now supported.


  * February 5, 2005 - Version 9.04 (Build 44.6)

   - added keyboard accelerators for device control


  * January 31, 2005 - Version 9.04 (Build 44.1)

   - fixed: the application crashed if MPEG2 was selected but the device does 
     not support it


  * November 4, 2004 - Version 9.04 (Build 43.4)

   - fixed: the selected video input was not correctly saved and restored


  * October 28, 2004 - Version 9.04 (Build 42.4)

   - added power management. Allows hibernation while previewing is active.


  * October 18, 2004 - Version 9.04 (Build 41.1)

   - added Zoom options for VMR9


  * October 12, 2004 - Version 9.04 (Build 40.1)

   - added Deinterlacing options for VMR9
   - save/restore the MPEG2 flag
   - added command-line parameters:
	/640		default to 640*480 on first launch
	/nocaption	starts application w/o caption and menu bar
	/fullscreen	starts application in fullscreen mode


  * July 23, 2004 - Version 9.03 (Build 33.5)

   - added delayed still capture


  * July 9, 2004 - Version 9.03 (Build 32.5)

   - disables screensaver while in fullscreen mode
   - fixed a possible crash when video capture reaches the 2GB size


  * June 17, 2004 - Version 9.03 (Build 29.4)

   - delay loaded WMVCore.dll in case Windows Media 9 Series is not installed
   - removed the "Mode" menu and replaced it with a toolbar. Only available when
     a DV camcorder is connected
   - fixed lack of audio in preview when used with a DV camcorder and VMR9 or
     still capture are enabled
   - fixed: keyboard shortcuts were not available in fullscreen mode (not VMR9)


  * May 31, 2004 - Version 9.02 (Build 23.1)

   - added support for hardware trigger (when hi-res still capture is enabled)
   - save/restore last TV channel
   - added the possibility of switching the TV channel by typing the channel on
     the keyboard. Always use 2 digits (e.g. channel #1 is 01) Use DEL or 
     BACKSPACE to correct the first digit
   - added PgUp / PgDn to switch to next / previous TV channel


  * May 19, 2004 - Version 9.02 (Build 17.3)

   - fixed a problem with the Window menu


  * May 10, 2004 - Version 9.02 (Build 17.1)

   - fixed: "Audio Format..." in the Options menu was not visible
   - added the Window > Remember Position menu option
   - added a warning if the requested capture file size is too large for the
     file system of the partition on which it is created
   - added a "Mode" menu to control a DV camcorder. All commands may not be 
     supported by the driver or the device
   - display full version numbers in About
   - added some links to my website in the Help menu
   - now shows progress while saving a WMV capture file
   - displays the actual capture file size after a capture


  * April 29, 2004 - Version 9.02 (Build 14.4)

   - added new shortcuts (capture, save)
   - arranged layout of controls in dialog boxes
   - remembers video compression/colorspace setting and compression settings
   - added an option to create a new capture file (in Allocate File Space) to
     preserve the current one(s)


  * April 16, 2004 - Version 9.01 (Build 12.5)

   - added support for full-screen mode support when VMR9 is enabled
   - added support for high-resolution still captures, only enabled if the
     driver implements a still pin


  * April 5, 2004 - Version 9.01 (Build 8.1)

   - remembers video standard and video size from previous session
   - added still capture
   - added Windows Media 9 Series compression


  * January 19, 2004 - Version 9.0 (Build 6.2)

   - added multi-monitor support (VMR9) requires DirectX 9.0 runtimes
   - remembers video input from previous session
   - added full screen mode support


  * Version 9.0 - 1st public custom version

   - added "caption bar and menu on and off" and "always on top" features


  * Version 9.0

    - inital build release by Microsoft in DirectX 9.0 SDK



Latest versions 
---------------

  The latest version of AMCap is always available from my web site:
  
    http://noeld.com/programs.asp?cat=video#AMCap



Contact details
---------------


  E-mail:

    webmaster@noeld.com


  WWW:

    http://noeld.com
