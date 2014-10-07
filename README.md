android-print-plugin-cups
=========================

CUPS print plugin for Android.

There are many other print plugins like this one, however I did not find any open-source plugins,
most of them have outrageous prices, and the only free plugin failed to work with Android printing framework.

In my opinion, printing support shall be a freely-available part of the OS,
that's also the reason why I chose GPL as a license for this plugin.

This plugin unpacks minimal Debian installation with CUPS included,
and launches it using PRoot, then uses it for actual printing.

To generate Debian image, download repo https://github.com/pelya/cuntubuntu
and launch script img-cups-jessie.sh from img directory.

You will need to do this from Debian/Ubuntu, and install few packages, specified in it's readme file.

PRoot can be downlaoded from http://proot.me/

Other than these things, the plugin contains only Java code, and no other magic.

There is no JNI or other weird stuff - Java code just calls lp, lpinfo, lpadmin etc commandline tools.

I hate Java and dislike IDEs, so you'll have to put up with my coding style, sorry.
Don't ask me how to import this project into Android Studio or Eclipse.


TODO:
=====

-   Implement AdvancedPrintOptionsActivity:
-     Page margins
-     Double-sided printing
-     Collate copies
-     Prints multiple document pages on each output page (-o number-up=16)
-     Fit to page
-     Resize print content to fit into less amount of pages, by reporting bigger paper size and rescaling it back when printing
-     All options configurable by lpoptions:
-      Paper type
-      Printer tray select
-      Print resolution
-   Print preview:
-    Show or hide print preview in advanced options
-    Change page margins inside print preview
-    Select and de-select pages for print preview
-   USB printers support, by forwaring calls from libusb to Java
-   Print on older devices and from older apps, using 'Share' button.
-   Print QR code with printer URL, support for Android intent to add a printer using this URL.
