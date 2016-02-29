Max ToolBox manual - 27/10/2009

By Nathanaël Lécaudé
maxtoolbox@studioimaginaire.com

The Max Toolbox was designed with the idea of automating and enhancing the process of patch editing within Max/MSP/Jitter.

Here is a list of the features included in this package :

Distribute selected objects in space, horizontally or vertically ;
Connect an outlet (selectable) of an object to the inlets (selectable) of a row of objects located below ;
Connect the outlets (selectable) of a row of objects to the inlet (selectable) of an object located below ;
Connect all (or less) of the outlets of an object to the inlets (selectable) of a row of objects located below ;
Connect the outlets (selectable) of a row of objects to all (or less) of the inlets of a an object located below ;
Connect the outlets (selectable) of a row of objects to the inlets (selectable) of a row of objects located below ;
Connect a column of two or more objects in cascade ;
Send any message(s) to the selected object(s) by invoking a dialog window using a keyboard shortcut ;
Access most of the features of this ToolBox using the same dialog window ;
Quickly name a row or column of objects ;
Create objects at the cursor position using keyboard shortcuts (à la Pure Data) (objects shortcuts are customizable) ;
Create objects at the cursor position using keyboard shortcuts and connect them to a previously selected object, either to the inlet or from the outlet depending on the mouse position.

Installing the ToolBox

The ToolBox contains the following files :

ToolBox.maxpat
This file should be placed in your extras folder.
maxtoolbox.maxpat
These files should be placed in the same folder in your search path.
toolboxhelp.maxpat
keyctrl.maxpat

maxtoolbox.js

toolbox\_config.js

mtb\_shortcuts.txt

mtb\_objects.txt


You will need to take all the files except ToolBox.pat and put them in a directory that is listed in your search paths.  It is strongly recommended to put the ToolBox.pat file in your Extras directory so you have a quick access to it.

Once the files are placed where they should go, load Max/MSP and select the ToolBox item in the Extas menu.  You should see a small window appear.  To start the Max ToolBox, click the "Load" button.  As long as this checkbox is checked, the ToolBox will start with Max. To unload the ToolBox (and prevent automatic startup), uncheck the checkbox.

First steps

There are usually two ways to access the functions of this ToolBox, either by pressing a key on the keyboard or by typing the name of the function in a dialog window.  From now on, let's refer to this dialog window as the “shell”.

The shell is the most powerful way to interact with the ToolBox and it is important to understand it well.

Accessing the shell
You can access the shell by pressing shift-r :  this will open a small window where you can enter text and process it by hitting enter.  Depending on the function you want to execute you might need to select objects prior to hitting shift-r.

What the shell can do
The shell is used to perform two different things :
Send messages to selected object(s) ;
Execute the ToolBox's different functions.

Sending messages to selected objects using the shell
Sending messages to selected objects is the same as creating a message box, writing a message in it, connecting it to some object(s) and clicking the message box.  The only difference is that it’s much faster to do so using the shell.  Here is how you would do it :
1.	Select one or several objects in your patch ;
2.	Hit the shell shortcut key (shift-r) ;
3.	Type the message you want to send in the dialog box ;
4.	Hit enter.

Note that you can also send separated messages the same way as in a message box using a comma.  You could therefore select several number boxes and send them the following messages without the quotes : “min 40, max 50”.  This would set all the selected number boxes to a minimum of 40 and a maximum of 50.  You can also send simple messages such as “bang” or set values of common GUI objects.

Executing ToolBox functions using the shell
While you can access most of the functions of this ToolBox using keyboard commands, (see reference) you can also use the shell to access those functions.  Certain functions will require the use of the shell because they need to be provided some arguments.  Functions are always called by preceding them with the “@” symbol to differentiate them from normal messages you send to objects.  When arguments are used, they are typed after the function’s name.  Here is an example :

To invoke the function that connects an outlet to the inlets of a row of objects you would first select the objects, hit shift-r, type “@sm”  and finally hit enter.  The connection functions can also accept arguments to choose which inlet and outlet to connect.  To connect outlet 3 of the top object to inlet 2 of the objects below, you would enter this in the shell instead : “@sm o 3 i 2”.

Functions that are not accessed by the shell
Most of the ToolBox’s functions can be accessed by the shell with the exception of the “Distribute” functions.  These functions will be explained here while the shell functions will be explained in the reference at this end of this document.

The “Distribute” function :
The distribute function can currently only be accessed using keyboard shortcuts.  This function includes vertical and horizontal distribution.  To distribute a row of objects, select the row and press “X” on the keyboard.  To distribute a column, press “Y”.  The row or column doesn’t need to be perfectly aligned to perform the distribution.  You can also dynamically distribute the objects by keeping your finger on the shortcut key.  After about half a second, moving the mouse horizontally for the horizontal distribution and vertically for the vertical distribution will space the objects in relation with the cursor position.  Notice that the title bar of the window shows the amount of pixels between each object.  You can use both “X” and “Y” shortcuts at the same time to form nice diagonals.

Notes : The distribution functions will work best with objects of the same size.  Diagonal distribution (by pressing and holding both shortcut keys) works best if the objects are already grossly aligned in a diagonal manner.

Choosing inlets and outlets for the connection functions

There are 2 ways of choosing inlets and outlets when connecting objects.  If you are using the keyboard shortcut to execute the function, you can type a sequence of keystrokes to choose which inlet and/or outlet to connect.

Let’s say you want to connect outlet 2 to inlet 3, you would type the following sequentially :

“shift-o 2 shift-i 3” and then the keyboard shortcut of the connection you want to make.  You could also type only “shift-o 2” before connecting if the first inlet is the destination (the default is always 1).

Note that this works almost the same as when using arguments, the order of the arguments provided to the shell is not important, you can type something like this : “@sm o 2 i 3” or “@sm i 3 o 2” which would give the same result.  You can also type only what is needed, if you want to connect outlet 2 to inlet 1, you can simply type “@sm o 2”.

For the connect cascade (shift-c) function, you can specify a number of connections to make by pressing shift-n with a number.



















Reference

Connect single to multiple
Shortcut key
q
Shell command
@sm
Arguments
o n i n  (where n  is the inlet or outlet number to connect, optional)
Description
This will connect an outlet of an object to the inlets of a row of objects located below.  You can choose which outlet or inlets to connect by typing a key sequence before hitting Q (see explanation at the end of this document).

Connect multiple to single
Shortcut key
a
Shell command
@ms
Arguments
o n i n  (where n  is the inlet or outlet number to connect, optional)
Description
This will connect the outlets of a row of objects to the inlet of an object located below.  You can choose which outlet or inlets to connect by typing a key sequence before hitting A (see explanation at the end of this document).

Connect cascade
Shortcut key
shift-c
Shell command
@cc
Arguments
o n i n  (where n  is the inlet or outlet number to connect, optional)
Description
This will connect a column of objects in cascade.  You can choose which outlet or inlets to connect by typing a key sequence before hitting C (see explanation at the end of this document).

Connect single to row
Shortcut key
w
Shell command
@sr
Arguments
o n i n  (where n  is the inlet or outlet number to connect, optional)
Description
This will connect the outlets of an object to the inlets of a row of objects located below.  You can choose which outlet or inlets to connect by typing a key sequence before hitting S (see explanation at the end of this document).

Connect row to single
Shortcut key
S
Shell command
@rs
Arguments
o n i n  (where n  is the inlet or outlet number to connect, optional)
Description
This will connect the outlets of a row of objects to the inlets of an object located below.  You can choose which outlet or inlets to connect by typing a key sequence before hitting W (see explanation at the end of this document).




Connect row to row
Shortcut key
e
Shell command
@rr
Arguments
o n i n  (where n  is the inlet or outlet number to connect, optional)
Description
This will connect the outlets of a row of objects to the inlets of a row of objects located below.  You can choose which outlet or inlets to connect by typing a key sequence before hitting E (see explanation at the end of this document).

Name a row or column of objects
Shortcut key
None
Shell command
@name
Arguments
-v (when naming a column)
Description
This will name a row or column of objects.  To use, select the row or column and press cmd/ctrl-r to open the shell, type “@name nameofobject1 nameofobject2 nameofobject 3 …”  When naming a column you need to use this syntax instead : “@name –v nameofobject1 nameofobject2 nameofobject 3 …”.



