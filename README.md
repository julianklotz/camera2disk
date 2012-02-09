camera2disk
===========

The Problem
-----------
To motivation to write this script was simple: I was sick of manually creating folders, copying and renaming files anytime I wanted to get photos from my digital camera. This simple bash script takes care of this problem.

The Idea
--------
This script copies image files from your camera to your computer.
It automatically creates a folder on your disk from the current date and the first argument supplied to the script, copies the files from your camera and renames them properly.

Installation
-----------
Download camera2disk from github. Copy it to a folder that is covered by your system’s $PATH variable. chmod it to be executable, e.g. 755.
After this is done, you will need to change the file camera2disk with you favourite text editor.
Change the line containing SOURCE\_PATH to the path to which your camera’s memory card is mounted. In my case, this is something like /Volumes/digicam/PANA\_102.
Then, change TARGET\_PATH to the folder where you keep your photos. If your camera produces file formats that are not covered in EXTENSIONS, you need to add these formats. Just stick to the format of the existing ones, it’s easy!

Example Usage
-------------
    $ ./camera2disk snapshots_sunset
...results in a folder in your image directory, named e.g. 120119\_snapshots\_sunset. This folder contains three subfolders (original, selection, web). The image files are placed in "original", named 120119\_snapshots\_sunset\_<orig_file_name>.<extension>

Versions
--------
### Version 1.0
  initial release

### Version 1.1
  dynamic, user serviceable file extension support, see $EXTENSIONS for reference

### Version 1.2
  until 1.1, this script blindly copied all files on your camera's memory card to the target folder. Now, only images that were created since you ran camera2disk for the last time are taken.
