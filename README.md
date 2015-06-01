
UT4 Converter Readme file
------------------------------

- Version: 0.4-DEV
- Author: XtremeXp
- Release Date: 08/05/2015 (0.3.0)
- Download latest released version at: http://utforums.epicgames.com/showthread.php?t=588848
- Source Code: https://github.com/xtremexp/UT4Converter


Description
------------------------------
UT4 Converter helps converting maps from Unreal (Tournament) previous games
to Unreal Tournament 4.


UT games supported
------------------------------
- Unreal 1
- Unreal Tournament (1999)

Some other games might be supported in the future.

If you want to convert UT games to Unreal Tournament 3,
download and use UT3 Converter program instead of UT4 Converter.

What is converted
------------------------------
- Brushes (mostly good but textures alignement may not be correct sometimes)
- Movers (working good except for doors (the current ut4 lift actor does not handle good door right now))
- Pick-ups (most of them)
- Lightning (color good but brightness a bit 'high', also note that "ZoneInfo" actors from UT99
are not converted)

What is NOT converted
------------------------------
- Models
- Textures
- Music
- All custom scripts
- Some special actors such as TriggerEvent, ...

Requirements
------------------------------
* Windows 7 / Vista / 8 - 64 Bit Operating System
* Java > 1.8.0_40 . www.java.com
* Unreal Tournament 4 (2015) Editor
* One of the following previous UT games:
*  Unreal 1
*  Unreal 2
*  Unreal Tournament
*  Unreal Tournament 2003
*  Unreal Tournament 2004
*  Unreal Tournament 3
* NConvert texture conversion program: http://www.xnview.com/en/nconvert/
* UModel Unreal ressource program extractor: http://www.gildor.org/en/projects/umodel

Installation and first start
------------------------------
Install nconvert http://www.xnview.com/en/nconvert/
Install umodel http://www.gildor.org/en/projects/umodel
Decompress the ZIP archive to any folder of your choice.
Double-click on UT4-Converter-<version>.jar, the program should be launching.

If not, make sure you have installed latest Java tecknology version at www.java.com
and create some "run.bat" batch file with notepad that you will save in the 
program folder with this command line:
"java -jar UT4-Converter-<version>.jar" (will force launching this file associating it 
as java program)
Go to Settings and set the unreal games folders as well as umodel and nconvert program paths

How to convert map?
------------------------------
Make sure you are allowed to convert the original map (if you are not the original author for example)

In UT4 Converter:
- Launch UT4 Converter
- Go to "Convert -> <Unreal Tournament X/Unreal X> Map"
- In the conversion settings, press "Select" and choose the map
- Press ok and wait while the conversion is running (it might takes several minutes)

In UT4 Editor:
- Open the UT4 Editor
- Create new level ("File -> New level ...") and select "Empty level"

- Import sounds
-- Browse to /Maps/WIP/<MapName>-UT99/U1 path using the internal browser
-- Click on "Import" and select converted sound files from <UT4ConverterPath>/Converted/<MapName>/Sounds
-- Make sounds loop if needed (double click on it and set "looping" to true). Generally sounds with name containing "loop" word are loop sounds
(e.g:  "AmbOutside_Looping_waves4")

- Import Textures
-- Browse to /Maps/WIP/<MapName>-UT99/U1 path using the internal browser
-- Click on "Import" and select converted sound files from <UT4ConverterPath>/Converted/<MapName>/Textures
-- After import, right click on all texture in editor and choose "create material"

- Import converted map
-- In menu, go to "File -> Import ..."
-- Select the file <UT4ConverterPath>/Converted/<MapName>/Level/<MapName>-<X>/U1.t3d
-- click on OK to import the map
- Rebuid Geometry ("Build" -> "Build Geometry")



Note:
- If after conversion your map got some bsp holes, remove all
"sheet" brushes (e.g: flat lava/water surface, they are generally colored in "green" color in UT/U1 editor).
 The converter does remove most of them, but not all of them yet.


Limitations / Issues
------------------------------
- Extraction of sound ressources only works with Windows
- Movers are replaced with lift actor which won't work correctly for doors
- Since Unreal Engine 4 does not support sheet brushes (e.g: flat lava/water surface, ...) , and as the converter
does not remove all of them, some "bsp holes" may appear (in that case try to find out all these brushes
and remove them until bsp holes dissapear)

License
------------------------------
License to be determined / set. No commercial use allowed. Just feel free to browse code or/and 
contribute !

MAKE SURE YOU GOT AUTHORISATION OR ARE ALLOWED TO CONVERT MAP BEFORE DOING IT.
YOU ARE THE ONLY ONE RESPONSIBLE FOR ANY COPYRIGHT INFRINGMENT RELATIVE TO 
CONVERTED MAP.

How to build and run latest version ?
------------------------------
With Netbeans IDE:
- Download and install latest Java 8 JDK: http://www.oracle.com/technetwork/java/javase/downloads/index.html
- Download and install Netbeans IDE: https://netbeans.org/downloads/ ("Java SE" version works but you can download full version)
- Open Netbeans and in Menu, go to "Team -> Git -> Clone.."
- Set "Repository URL" = https://github.com/xtremexp/UT4Converter
- Click "Next" and select "Master" to get latest code (you may select other branches if you want to)
- Click "Finish" and wait while project is being imported.
Project will be saved by default in C:\Documents and Settings\<username>\My Documents\NetbeansProject\UT4Converter
- Right-Click on project and press "Run". At first time it might take several minutes to download required librairies.

With Eclipse IDE:
- Download and install latest Java 8 JDK: http://www.oracle.com/technetwork/java/javase/downloads/index.html
- Download and install "Eclipse for Java Developers": https://eclipse.org/downloads/
- Open "Eclipse" Right-click in "Package Explorer" view then "New -> Project..", "Maven" -> "check out Maven projects from SCM"
- Click "Next"
- Set "SCM Url" to: "https://github.com/xtremexp/UT4Converter.git"
- Click "Finish"
- Right click on "UT4-Converter" project then "Run as" -> "Java application"


Libraries / Technologies used
------------------------------
- Java 1.8.0_40 - http://www.java.com
- Java Vecmath library - 1.3.1 - https://java.net/projects/vecmath
- Texture Toolkit for UnrealEd by Alex Stewart - 1.0 - http://www.foogod.com/UEdTexKit/
- Java Targa image reader by Rob Grzywinski / Reality Interactive, Inc.

Converter interfaces the external tools:
- Nconvert by Pierre-E Gougelet - 6.70
- UModel by Konstantin Nosov

History
------------------------------
- 0.4.0 - In Progress:
  * Added support for Unreal Tournament 2003 / 2004, Unreal 2, Unreal Tournament 3
  * Added conversion for textures
  * [UI] Added advanced conversion settings
  * [UI] 
  * Fixed sounds not being exported from map package
  * Fixed frozen UI on map conversion
  * ?

- 0.3.0 - 08/05/2015:
  * Improved lightning (brightness, lightning type, ...)
  * Sound export and conversion
  * Added LiftExit, Jumppad and BlockAll for conversion
  * Converts Triggers with "CapsuleTrigger" volume
  * Better alignment of FlagBases
  * UI: improved log display
  * Fixed crash if UT4 converter has whitespace in one of his parent folders
  * Added / Activated support for Unreal 1
  * Auto-creates big additive brush to simulate level in subtract mode and lightning importance volume for level 

- 0.2.1 - 19/04/2015: 
  * Fixed movers not importing correctly in UT4 editor

- 0.2.0 - 18/04/2015: 
  * [UI] Added conversion log display
  * Fixed conversion crash with some maps with incorrect name prefix
  * Added support for UT99 Binary maps (.unr) as input file
  * Improved mover conversion (moving good now)
  * Added LavaZone, SlimeZone, WaterZone conversion
  * Added missing weapons conversion for
  "FlakCannon", "AutoMag", "Enforcer","doubleenforcer",
"ImpactHammer", "ASMD", "Rifle", "Minigun", "SuperShockRifle" (instagib)
  * Added teleporter conversion
  * Added conversion for powerup "invisibility", "ut_invisibility",
 "ut_stealth", "nalifruit" (replaced with normal health),
 "bandages" (replaced with healthvial), "PowerBelt"
  * Added conversion for ammo "Sludge", "EClip", "FlakShellAmmo", "ASMDAmmo",
 "RifleAmmo", "RifleRound", "RifleShell", "Minigun", "SuperShockRifle" (instagib)
  * Removed unecessary auto-created notes for unconverted actor
for PathNodes, InventorySpot, TranslocDest
...

- 0.1.0 - 13/04/2015: 
  * First version with basic brush, lights and pickups conversion

