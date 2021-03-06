debug-icons-oxygen-4
====================

![Icon](https://raw.githubusercontent.com/debug-icons-project/debug-icons-oxygen-4/master/16x16/actions/application-exit.png)![Icon](https://raw.githubusercontent.com/debug-icons-project/debug-icons-oxygen-4/master/22x22/apps/accessories-calculator.png)![Icon](https://raw.githubusercontent.com/debug-icons-project/debug-icons-oxygen-4/master/24x24/categories/applications-science.png)![Icon](https://raw.githubusercontent.com/debug-icons-project/debug-icons-oxygen-4/master/32x32/devices/input-mouse.png)![Icon](https://raw.githubusercontent.com/debug-icons-project/debug-icons-oxygen-4/master/48x48/mimetypes/image-x-generic.png)![Icon](https://raw.githubusercontent.com/debug-icons-project/debug-icons-oxygen-4/master/64x64/places/start-here.png)

The goal of the debug-icons-project is to create icon themes which can be used to a) debug and modify existing icon themes, b) check the correct usage of icons in UIs/DEs or c) as a basis for new themes. In addition, the project provides a set of Python scripts which can be used to easily modify, extend and update the icon themes.

The variant `debug-icons-oxygen-4` is based on the Oxygen icon theme for KDE 4 and covers all its icons (except flags and animations). Since the official site currently offline (June 2014), the latest Oxygen version was downloaded from: http://download.kde.org/stable/4.13.2/src/oxygen-icons-4.13.2.tar.xz

Usage
-----

###Installation
Right now there is no direct way to download the icon theme so you have use git to make a local copy of the theme:

    git clone https://github.com/debug-icons-project/debug-icons-oxygen-4.git


Copy the folder `debug-icons-oxygen-4` and all the containing files to the corresponding icon folder of you system. For KDE this might for example be `~/.kde/share/icons`. Another default location is `/usr/share/icons`. After copying the data, the new icon theme should show up in the system settings (in KDE: System Settings -> Common Appearance and Behavior -> Application Appearance -> Icons).

If you also want to update and extend the icon theme from time to time, you have two possibilities: either run the script(s) and copy the updated icon theme to one of the aforementioned places or b) make a symlink in one of those places which links to wherever you put the whole debug-icons project folder. This way you don't have to copy the updated themes every time, but it is very likely that you still have to switch the icons theme or flush the icon cache. Otherwise new or updated icons might not be recognized.

###Description of icons
Each icon contains the following information:

* Each icon in the theme contains a unique six letter ID which can be used to look up the corresponding **filename**. For the most common icons the ID is an abbreviation of the filename but for others it is just a random number. The file lookup_icons.txt in the main theme folder contains all ID/filename pairs. For larger icon sizes, the filename is also directly visible on icon itself.

* The **context** of the icon can be either determined from the first two letters of the automatically generated IDs (e.g. MI0323 is a MimeType icon) or from the background color of the icon. For larger icon sizes, the context is also visible on icon itself.

* Except for the smallest icon size (16x16) each icon includes its **size** in pixel in the lower left corner.

* The caption of each icon is done with a non-aliased font which means that if an icon is displayed in a **wrong size** (e.g. a 48x48 icon is displayed at a 45x45 size) the text will most likely look blured and unsharp. If the icon is displayed correctly, the text must be crisp and sharpp.

###Fall-back theme for another icon theme
If you are developing a new icon theme or want to extend an existing icon theme it might make sense to set debug-icons as a fallback icon of your icon theme. This way, all missing icons of your theme will be replaced with icons from the debug-icons theme. This makes finding the correct filenames of missing icons much easier.

In order to do so add the debug-icons theme to your theme file. At the top of the file there should be a line similar to:

    Inherits=gnome,hicolor

Change this line to

    Inherits=debug-icons-oxygen-4,gnome,hicolor
    
Now all icons which are not present in your theme should be replaced with icons from the debug theme.

Changelog
--------
* 2014-06-29 First official version

Contact
---------
For bug reports please open an issue on the project page: https://github.com/debug-icons-project/debug-icons-oxygen-4

If you have questions, comments or requests you can also send me an email: jnmllr42 (at) gmail.com

License
-----------
The icon theme and all corresponding files are licensed under the Creative Common Attribution-ShareAlike 4.0 International (CC BY-SA 4.0) license (see http://creativecommons.org/licenses/by-sa/4.0/ ). 
