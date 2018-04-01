
<p align="center">
  <img align="middle" src="src/vi/ui/res/logo.png">
</p>
# Welcome To Vintel+

## Features
Update to 2.0.0

## Bug fix
Chatroom filename

## What is Vintel+

Visual intel chat analysis, planning and notification application for [EVE Online](http://www.eveonline.com). Gathers status through in-game intelligence channels on all known hostiles and presents all the data on a [dotlan](http://evemaps.dotlan.net/map/Cache#npc24) generated regional map. The map is annotated in real-time as players report intel in monitored chat channels.

Vintel+is written with Python 2.7, using PyQt4 for the application presentation layer, BeautifulSoup4 for SVG parsing, and Pyglet for audio playback.

Vintel+ is a fork to [Vintel](https://github.com/Xanthos-Eve/Vintel+/issues)

## Features

 - Platforms supported: Mac, Windows and Linux.
 - A pilot may be KOS-checked right from in-game chat channels.
 - Quick batch KOS-checking of the Local system when foregrounding Vintel+.
 - Notifications and alarms can be spoken using text-to-speech on select platforms (currently only OS X).
 - "TheCitadel", "North Provi Intel", and "North Catch Intel" are merged to one chat stream. You can add or remove channels via a menu option.
 - An interactive map of Providence / Catch is provided. Systems on the map display real-time intel data as reported through intel channels.
 - Systems on the map display different color backgrounds as their alarms age, with text indicating how long ago the specific system was reported. Background color becomes red when a system is reported and lightens (red->orange->yellow->white) in the following intervals: 4min, 10min, 15min, and 25min.
 - Systems reported clear display on the map with a green background for 10 minutes.
 - Clicking on a specific system will display all messages bound on that system. From there one can can set a system alarm, set the sytems clear or set it as the current system for one or more of your characters.
 - Clicking on a system in the intel channel causes it to be highlighted on the map with a blue background for 10 seconds.
 - The system where your character is currently located is highlighted on the map with an violet background automatically whenever a characater changes systems.
 - Alarms can be set so that task-bar notifications are displayed when an intel report calls out a system within a specified number of jumps from your character(s). This can be configured from the task-bar icon.
 - The main window can be set up to remain "always on top" and be displayed with a specified level of transparency.
 - Ship names in the intel chat are marked blue.

## Usage

 - Manually checking pilot(s) using an EVE client chat channel:
 Type xxx in any chat channel and drag and drop the pilots names after this. Vintel+ recognizes this as a request and checks the pilots listed.
 - Checking all pilots in the local system:
This option must first be activated by checking the Vintel+ app menu: Menu > Auto KOS-Check Clipboard.
To use this feature: click on a pilot in the local pilot list and then type the shortcuts for select-all and copy-selection. This places the pilots in local on your clipboard. Next switch to the Vintel+ app momentarily and back to Eve. KOS checking of these pilots will continue in the background.


## KOS Results

"KOS" status values reported by Vintel+

 - **KOS**: the pilot is known as KOS to the alliance and has been marked as such in the KOS-checker system.
 - **RED by last**: the last player (non-NPC) corp in the pilot's employment history is KOS.
 - **Not KOS**: the pilot is known as NOT KOS to the alliance and has been marked as such in the KOS-checker system.
 - **? (Unknown)**: the pilot is not known by the KOS-checker system and there are no hostile corporations in her employment history.


## Running Vintel+ from Source

To run or build from the source you need the following packages installed on your machine. Most, if not all, can be installed from the command line using package management software such as "pip". Mac and Linux both come with pip installed, Windows users may need to install [cygwin](https://www.cygwin.com) to get pip. Of course all the requirements also have downoad links.

The packages required are:
- Python 2.7.x
https://www.python.org/downloads/
Vintel+ is not compatible with Python 3!
- PyQt4x
http://www.riverbankcomputing.com/software/pyqt/download
Please use the PyQt Binary Package for Py2.7
Vintel+ is not compatible with PyQt5!
- BeautifulSoup 4
https://pypi.python.org/pypi/beautifulsoup4
- Pyglet 1.2.4 (for python 2.7)
https://bitbucket.org/pyglet/pyglet/wiki/Download
pyglet is used to play the sound – If it is not available the sound option will be disabled.
- Requests 2
https://pypi.python.org/pypi/requests
- Six for python 3 compatibility https://pypi.python.org/pypi/six

## Building the Vintel+ Standalone Package

 - The standalone is created using pyinstaller. All media files and the .spec-file with the configuration for pyinstaller are included in the source repo. Pyinstaller can be found here: https://github.com/pyinstaller/pyinstaller/wiki.
 - Edit the .spec file to match your src path in the "a = Analysis" section and execute "pyinstaller Vintel+.spec Vintel+.py". If everything went correctly you should get a dist folder that contains the standalone executable.
